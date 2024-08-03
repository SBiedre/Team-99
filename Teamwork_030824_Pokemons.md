```py
#Task 1 - Calculate the percentage of pokemon with Type 1 == Water
total_pokemon = len(pokemon_df)
water_pokemon = len(pokemon_df[pokemon_df['Type 1'] == 'Water'])
water_percentage = round(((water_pokemon / total_pokemon) * 100),2)

print('Total:', total_pokemon)
print('Water type pokemons:', water_pokemon)
print("Percentage of Water type pokemon:", water_percentage)

# Task 2 - What is the maximum 'Speed' value? What is the minimum 'Speed' value? What is the difference between max and min 'Speed'?
max_speed = pokemon_df['Speed'].max()
min_speed = pokemon_df['Speed'].min()
speed_difference = max_speed - min_speed

print("Maximum speed:", max_speed)
print("Minimum speed:", min_speed)
print("Difference between max and min speed:", speed_difference)

# Task 3 Filter the DataFrame to include only the Pokemon with 'Speed' >= 80. How many Pokemon meet this criterion? Display this DataFrame using your preferred visualization method.
speed_above80 = pokemon_df[pokemon_df['Speed'] > 80]
number_of_pokemons80 = len(speed_above80)
print('The number of pokemons with speed above 80 is', number_of_pokemons80)
type_counts = speed_above80['Type 1'].value_counts()
plt.figure(figsize=(10, 6))
type_counts.plot(kind='bar', color='blue')

plt.title('Count of Pokemon Types with Speed > 80')
plt.xlabel('Type 1')
plt.ylabel('Number of Pokemon')
plt.xticks(rotation=45)
```
