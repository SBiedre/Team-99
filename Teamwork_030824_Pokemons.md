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
#Filter the DataFrame to include only the Pokémon with 'Speed' >= 80. How many Pokémon meet this criterion? Display this DataFrame using your preferred visualization method.


speed_greater_or_equal_80 = pokemon_df[pokemon_df['Speed'] >= 80]
print("Number of Pokémon with Speed >= 80:",(len(speed_greater_or_equal_80)))

print(speed_greater_or_equal_80)

# Visualization: Bar plot of counts by 'Type 1'
plt.figure(figsize=(10, 6))
speed_greater_or_equal_80['Type 1'].value_counts().plot(kind='bar', color='skyblue')
plt.title('Count of Pokémon with Speed >= 80 by Type 1')
plt.xlabel('Type 1')
plt.ylabel('Count')
plt.xticks(rotation=90)
plt.show()

# Task4
# Find Pokémon with the longest name (excluding spaces)? What is this pokemons name?

pokemon_name_lengths = pokemon_df['Name'].apply(lambda x: len(x.replace(" ", "")))
longest_name_index = pokemon_name_lengths.idxmax()
longest_pokemon_name = pokemon_df.loc[longest_name_index, 'Name']
print(f"The Pokémon with the longest name is: {longest_pokemon_name}")
```
