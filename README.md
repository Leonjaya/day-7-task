# day-7-task
const asiaCountries = countries.filter(country => country.region === 'Asia');
console.log(asiaCountries);

@Leonjaya
Owner
Author
const lowPopulationCountries = countries.filter(country => country.population < 200000);
console.log(lowPopulationCountries);

@Leonjaya
Owner
Author
countries.forEach(country => {
console.log(Name: ${country.name.common}, Capital: ${country.capital ? country.capital[0] : 'N/A'}, Flag: ${country.flags[1]});
});

Owner
Author
const totalPopulation = countries.reduce((total, country) => total + country.population, 0);
console.log(Total Population: ${totalPopulation});
Owner
Author
const usdCountries = countries.filter(country => country.currencies && Object.values(country.currencies).some(currency => currency.code === 'USD'));
console.log(usdCountries.map(country => country.name.common));
Owner
Author
fetch('https://restcountries.com/v3.1/all')
.then(response => response.json())
.then(countries => {
// 1. Get all the countries from Asia continent/region
const asiaCountries = countries.filter(country => country.region === 'Asia');
console.log('Asian Countries:', asiaCountries);

// 2. Get all the countries with a population of less than 200,000
const lowPopulationCountries = countries.filter(country => country.population < 200000);
console.log('Countries with population less than 200,000:', lowPopulationCountries);

// 3. Print the name, capital, and flag of each country
countries.forEach(country => {
  console.log(`Name: ${country.name.common}, Capital: ${country.capital ? country.capital[0] : 'N/A'}, Flag: ${country.flags[1]}`);
});

// 4. Print the total population of countries
const totalPopulation = countries.reduce((total, country) => total + country.population, 0);
console.log(`Total Population: ${totalPopulation}`);

// 5. Print the country that uses US dollars as currency
const usdCountries = countries.filter(country => country.currencies && Object.values(country.currencies).some(currency => currency.code === 'USD'));
console.log('Countries using USD:', usdCountries.map(country => country.name.common));
})
.catch(error => console.error('Error fetching countries data:', error));
