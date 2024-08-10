# Correlation, dataframe filtering
```py
grass_df = pokemon_df.loc[pokemon_df['Type 1'] == 'Grass']

#sns.regplot(x = 'Attack', y = 'Defense', data = grass_df) 
#plt.title('Attack vs Defense for Grass Pokemons')

correlation_grass = round(grass_df["Attack"].corr(grass_df["Defense"]), 3)
print(f'Correlation between Attack and Defense for Grass Type 1 Pokemons is {correlation_grass}')

# create Dataframe for Type 1 Water type
water_df = pokemon_df.loc[pokemon_df['Type 1'] == 'Water']
#water_df.head()
#sns.regplot(x = 'Attack', y = 'Defense', data = water_df) 
#plt.title('Attack vs Defense for Water Pokemons')
correlation_water = round(water_df["Attack"].corr(water_df["Defense"]), 3)
print(f'Correlation between Attack and Defense for Water Type 1 Pokemons is {correlation_water}')

sns.regplot(x='Attack', y='Defense', data=grass_df, marker='^', color='green', label='Grass Pokemons')
sns.regplot(x='Attack', y='Defense', data=water_df, marker='v', color='blue', label='Water Pokemons')

plt.xlabel('Attack')
plt.ylabel('Defense')
plt.title('Regression Plot with Grass and Water Type Pokemons')
plt.legend()
```
