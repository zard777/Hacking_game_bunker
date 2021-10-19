_Crown Trick money inf._


> **use CE, memory view, (ctrl + A), paste and execute**
 
**Block of codes**

```lua
{$lua}
function getInsForJump(address,registername,destination,allocsize,SharedMemoryName)
  address = getAddressSafe(address)
  if address==nil then error('getInsForJump address nil') return end
  if allocsize==nil then allocsize=4096 end
  destination=getAddressSafe(destination)
  if destination==nil then
	if SharedMemoryName==nil then destination = allocateMemory(allocsize,address)
	else destination = allocateSharedMemory(SharedMemoryName,allocsize) end
  end
  local size = (address+5-destination>0x7FFFFFFF) and 14 or 5
  if registername~=nil then
	unregisterSymbol(registername)
	registerSymbol(registername,destination,true)
  end
  local opcodes = {}
  local i = 0
  while(i<size) do
    local ext, opc=splitDisassembledString(disassemble(address+i))
    opcodes[#opcodes+1] = opc
    i=i+getInstructionSize(address+i)
  end
  local copy = table.concat(opcodes,'\r\n')
  local readAsTable = true
  local byt = readBytes(address,i,readAsTable)
  for j=1,#byt do byt[j] = ('%02X'):format(byt[j]) end
  local bytes = table.concat(byt, ' ')
  return i,copy,bytes,size,destination
end

function enablescript(name,registername,addressname,script,disable)
	local address=getAddress(addressname)
	if disable then script=(script):format(address,registername,readBytes(registername,1))
	else
		local i,copy,bytes,size =getInsForJump(address,name)
		script=(script):format(registername, registername, name, copy, registername, i, bytes, address)..string.rep('nop\n',i-size)..'returnhere:'
	end
	local success=autoAssemble(script)
	if disable then
		if not success then error(name..' autoAssemble failed')
		else
			deAlloc(name)
			unregisterSymbol(name)
			unregisterSymbol(registername)
		end
	else
		if not success then
			deAlloc(name)
			unregisterSymbol(name)
			error(name..' autoAssemble failed')
		end
	end
end

if syntaxcheck then return end


LaunchMonoDataCollector()
[ENABLE]
enablescript('CurrencyDataSet_alloc','CurrencyDataSet_save','CurrencyData:Set',[[
label(newmem)
label(returnhere)
label(%s)
registersymbol(%s)

%s:
newmem:
movsd xmm2,[value]
%s
jmp returnhere
value:
dq (double)9890
%s:
db %X %s
%X:
jmp newmem
]])

miMonoActivateClick(sender)

[DISABLE]
enablescript('CurrencyDataSet_alloc','CurrencyDataSet_save','CurrencyData:Set',[[
%X:
readmem(%s+1,%u)
]],true)

miMonoActivateClick(sender)
```
