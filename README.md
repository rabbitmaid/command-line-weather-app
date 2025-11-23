# WeatherApp

Simple command-line PHP utility that fetches and displays current weather for a given city.

**Features**
- Fetches weather data using the project's `WeatherService` and outputs a concise summary to the console.

**Requirements**
- PHP (cli) installed on your system.
- Composer (to install/update PHP dependencies) — the project includes a `vendor/` directory already.

**Configuration**
Before running the app, copy `.env.example` to `.env` and set the required OpenWeather values:

```
OW_APP_KEY=your_openweather_api_key_here
OW_API_URL=http://api.openweathermap.org/data/2.5/weather
```
These values are required for the app to fetch data from the OpenWeather API.

**Installation**
1. If you don't have dependencies installed, run:

```powershell
composer install
```

2. Ensure `vendor/autoload.php` is available (the repository already contains `vendor/` in this workspace).

**Usage**
Run the script from the project root with a city name argument:

```powershell
php weather.php "City Name"
```

Example:

```powershell
php weather.php Yaounde
```

**Project Structure**
- `weather.php`: CLI entrypoint — parses arguments and prints weather output.
- `src/WeatherService.php`: Service that handles fetching/parsing weather API responses.
- `composer.json`: Composer manifest for this project.
- `vendor/`: Composer-installed dependencies and autoloader.
- `note.md`: Example API response snapshot used for reference.

**Example API Response**
The `note.md` file contains a sample API JSON response similar to what the service returns. Example fields include `lat`, `lon`, `timezone`, and an array of `data` elements with `temp`, `feels_like`, `pressure`, `humidity`, `wind_speed`, and `weather` (description and icon).

**Developer notes**
- The script uses Composer autoloading: make sure `require 'vendor/autoload.php'` in `weather.php` points to the correct path.
- `src/WeatherService.php` is the place to update parsing, units, or the API endpoint.
- If you want to change the output format (JSON/plain text), update `weather.php` to format the `WeatherService` result.

**Troubleshooting**
- If you get network or API errors, check your network and any API keys (if the service requires them).
- To debug, add temporary `var_dump()` or logging in `src/WeatherService.php`.

**Contributing**
- Feel free to submit PRs for unit tests, error handling improvements, or adding options (units, language, caching).

**License**
- This project is licensed under the MIT License. See the `LICENSE` file in the project root for the full text.
- The `LICENSE` file currently names "Your Name" as the copyright holder; replace this with the correct
	name and year for your project (e.g., `Copyright (c) 2025 RabbitMaid`).
