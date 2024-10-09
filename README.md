# Tubi TV Scraper

## Overview
This script scrapes live TV channel and Electronic Program Guide (EPG) data from Tubi TV using proxy servers. It generates M3U playlists and EPG XML files that can be used in media players such as VLC or Plex, providing a seamless live TV experience.

## New Features
This version of the Tubi TV scraper includes several new improvements:

- **Improved Logging**: Uses the `logging` module to replace `print()` statements, providing more control and allowing different log levels (e.g., `INFO`, `WARNING`, `ERROR`).
- **SSL Verification**: Ensures all HTTPS requests are verified securely using the `certifi` library, making data transfers more secure.
- **Command-Line Arguments**: Adds flexibility by allowing users to specify which countries to scrape data for and where to save the output files.
- **Retry Logic for Proxies**: Limits the number of retries for failed proxies to avoid excessive network requests.
- **Flexible Output Directory**: Allows users to specify the directory where output files (M3U and XML) should be saved.

## Usage
The script can be run with command-line arguments for added flexibility. Here is an example of how to use it:

```bash
python scrape-tubi.py --countries US --output-dir /path/to/save/files
```

### Arguments
- `--countries`: A space-separated list of country codes to scrape data for. Defaults to `US`.
- `--output-dir`: The directory where the generated M3U playlist and EPG XML files will be saved. Defaults to the current directory.

## Dependencies
The script requires the following Python libraries:

- `requests`
- `beautifulsoup4`
- `certifi` (for secure SSL verification)
- `argparse` (standard library)
- `logging` (standard library)

You can install these dependencies using the following command:

```bash
pip install requests beautifulsoup4 certifi
```

## Example Commands
- To scrape data for the US and save output in the current directory:
  ```bash
  python scrape-tubi.py --countries US
  ```
- To scrape data for multiple countries (`US`, `CA`) and save in a specific folder:
  ```bash
  python scrape-tubi.py --countries US CA --output-dir /home/user/tubi-output
  ```

## Features Overview
- **Logging**: Uses `INFO`, `WARNING`, and `ERROR` levels to differentiate messages, making it easier to debug issues and monitor script execution.
- **Proxy Support**: Automatically rotates through a list of proxies until a successful connection is made, ensuring stability and reliability.
- **Improved Security**: All HTTPS requests are verified to ensure secure communication with Tubi TV servers using SSL certificates.
- **Retry Limitation**: The `MAX_RETRIES` parameter prevents unnecessary retries, improving script efficiency and reducing network load.
- **Flexible Output Directory**: Specify the output directory to control where generated files are saved.

## Contributing
Contributions are welcome! If you'd like to contribute, please fork the repository, create a new branch for your changes, and submit a pull request.

### Contribution Guidelines
- Ensure that all new features are properly documented in the README.
- Add tests where appropriate to validate new functionality.
- Follow best coding practices to ensure consistency and readability.

## Changelog
### Version 2.0
- Introduced logging for better control over script output.
- Added SSL verification for secure proxy connections.
- Implemented command-line arguments for more flexibility in usage.
- Limited retries for proxies to prevent excessive network requests.

## How the Script Works
1. **Get Proxies**: The script retrieves a list of proxies for the specified country using ProxyScrape.
2. **Fetch Channel List**: Connects to Tubi TV via a proxy to fetch channel and EPG data.
3. **Generate Playlist and EPG Files**: Creates an M3U playlist and an XML EPG file, then saves them to the specified output directory.

## FAQ
- **Why do I need proxies?**
  Proxies help avoid rate-limiting and prevent being blocked by Tubi TV servers, ensuring continuous scraping without interruptions.

- **What if the script fails to get proxies?**
  If no proxies are found, the script will print a warning and skip the country.

- **How do I install dependencies?**
  Use the command `pip install requests beautifulsoup4 certifi` to install all required dependencies.

## License
This project is licensed under the MIT License - see the LICENSE file for details.



## How to Use the M3U Playlist

To use M3U playlist in your IPTV application, look for the option to import an M3U playlist within the app's settings. Once you find the import option, simply copy and paste the Playlist URL and EPG URL listed below into the respective fields.

### Playlist URL:
``https://bit.ly/tubi-m3u``

### EPG URL:
``https://bit.ly/tubi-epg``

## Disclaimer:

This repository has no control over the streams, links, or the legality of the content provided by tubitv.com. It is the end user's responsibility to ensure the legal use of these streams, and we strongly recommend verifying that the content complies with the laws and regulations of your country before use.
