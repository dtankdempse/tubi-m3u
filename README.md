# Tubi TV M3U Scraper

This repository contains a Python script (`scrape-tubi.py`) that scrapes Tubi TV for channel listings and creates M3U playlists along with XML EPG files. This version has been updated to improve reliability, flexibility, and usability compared to the older version (`scrape-tubi OG.py`).

## Features

- **Proxy Support**: Fetch Tubi TV channel listings via SOCKS4 proxies.
- **Improved Error Handling**: Detailed exception handling for SSL and connection issues.
- **Retry Mechanism**: Limit the number of retries per proxy to ensure efficient usage.
- **Logging**: Added logging for better debugging and monitoring.
- **Command-Line Flexibility**: Ability to specify countries using command-line arguments.
- **Automatic Output Directory**: Output files are saved in the same directory as the script, simplifying file management.
- **Timeout Control**: Proxy requests now have a timeout to prevent hanging on slow connections.

## Requirements

- Python 3.x
- Required Python packages:
  - `requests`
  - `beautifulsoup4`
  - `argparse`
  - `urllib3`

You can install the required dependencies using:
```bash
pip install requests beautifulsoup4
```

## Usage

### Basic Usage
```bash
python scrape-tubi.py --countries US
```

### Arguments

- `--countries`: Specify the country codes for which to fetch proxies and Tubi TV data. Default is `US`.

### Example
```bash
python scrape-tubi.py --countries US CA
```
This command fetches Tubi TV data for the US and Canada, saving output files to the same directory as the script.

## Improvements Over the Original Version

### Version 2.1

1. **SSL Warnings Suppressed**:
   - SSL warnings are now suppressed to avoid console clutter when using unverified HTTPS requests.

2. **Logging System Added**:
   - Replaced `print()` statements with a proper logging system for better control and information tracking.

3. **Retry Limit**:
   - Added a retry mechanism (`MAX_RETRIES = 10`) to prevent indefinite attempts to connect through unreliable proxies.

4. **Better Exception Handling**:
   - Enhanced exception handling, specifically for SSL errors and connection issues, leading to more robust proxy management.

5. **Flexible Command-Line Options**:
   - Added command-line arguments for specifying the list of countries, making the script easier to configure without code modifications.

6. **Timeout Parameter**:
   - Added a `timeout=10` parameter for all proxy requests, reducing the risk of the script hanging on slow connections.

7. **Automatic Output Directory**:
   - Files are now saved in the same directory as the script by default, making output management simpler and more predictable.

## Notes

- **Proxy Reliability**: The script uses free proxies from ProxyScrape, which may be unreliable. It is recommended to use paid proxies for consistent performance.
- **Security Warning**: SSL verification is disabled for proxy connections, which may pose security risks. Use this script in trusted environments only.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.




## How to Use the M3U Playlist

To use M3U playlist in your IPTV application, look for the option to import an M3U playlist within the app's settings. Once you find the import option, simply copy and paste the Playlist URL and EPG URL listed below into the respective fields.

### Playlist URL:
``https://bit.ly/tubi-m3u``

### EPG URL:
``https://bit.ly/tubi-epg``

## Disclaimer:

This repository has no control over the streams, links, or the legality of the content provided by tubitv.com. It is the end user's responsibility to ensure the legal use of these streams, and we strongly recommend verifying that the content complies with the laws and regulations of your country before use.
