### tested on version 1.1.1

<💡💡💡>

```
health isnt very easy. You only find the Healthbar value, but you need to find the real health value. 
used dnspy and looked into assembly-CSharp.dll.
You find more information with dnspy. When you did find something interesting you can use the Mono dissector and search for the class.

What I find is something like "setHP" looks good. 
I go to this function and go to the start of the function and give it a return and I see my health doesnt drop.
And from the enemys also. So I checked more and more addresses. 
After 10 I find max health, and with the structure data I find the current health.
Then I look what access this address and find the address where only the current health is.
```

+ Example: 

```csharp
Zombotron.Systems:PlayerEquipSystem:HealthChangedHandler+22
```
_ When you search ingame you find something like this:

```csharp
Zombotron.UI:HealthBar:set_Health+11
```
