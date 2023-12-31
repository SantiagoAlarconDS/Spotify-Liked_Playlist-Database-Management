# Spotify Liked Playlist Database Management

This project allows you to manage a song database by retrieving songs from Spotify and storing them in a MySQL database. It also provides the ability to send the added songs to a Telegram chat using a Telegram bot to download.

## Motivation
The motivation behind this project is to enable users to effortlessly download songs through Telegram and simultaneously maintain an organized record of their music collection. By automating the retrieval and storage process, the bot eliminates the need for manual data entry and ensures that each  song is seamlessly added to the database.

## Features
* Fetches songs from Spotify: The bot connects to the Spotify API and retrieves songs based on specified criteria, such as the number of songs to fetch.

* Stores songs in a MySQL database: The bot utilizes MySQL Connector to establish a connection with a MySQL server and store the fetched songs in a dedicated database table.

* Avoids duplicate entries: The bot checks the database for existing songs to prevent duplicates from being added.

* Sends new songs to Telegram: The bot can send newly fetched songs to a specified Telegram chat, allowing users to receive updates and notifications about the latest additions to their song database.

* Easy setup and configuration: The project provides clear instructions and a user-friendly interface to set up the Spotify API credentials and configure the MySQL database.

## Prerequisites

Before running the application, make sure you have the following dependencies installed:

- Python 3.11.4
- MySQL database server
- Spotify API credentials
- Telegram bot API token

## Setup Spotify API

To set up the Spotify API in the Spotify Developer Dashboard, follow these steps:

1. Go to the [Spotify Developer Dashboard](https://developer.spotify.com/dashboard/) and log in with your Spotify account.

2. Click on "Create an App" or "Create a New App" to create a new application.

3. Provide a name for your application and a short description.

4. Set the redirect URI(s) for your application. This is the URL where Spotify will redirect users after they grant permission to your application. In this case set it to `http://localhost:8888/callback`.
 
5. Click on "Save", you will be redirected to the application dashboard.

6. Click on "Settings" and note down the "Client ID" and "Client Secret" values. You will need these to authenticate and access the Spotify API in the file /classes/info.py.

## Installation

1. Clone the repository:

   ```bash
   git clone git clone git@github.com:SantiagoAlarconDS/Spotify-Liked_Playlist-Database-Management.git
   ```

2. Install the required dependencies:

   ```bash
   pip install -r requirements.txt
   ```

3. Configuration:

   - Spotify API credentials: Open the `classes/info.py` file and replace the `spotify_client_id` and `spotify_client_secret` with your own Spotify API credentials.

   - Telegram bot: Open the `classes/info.py` file and replace the `chat_id`,`api_id`,`api_key`,`api_hash` with your Telegram bot API token.
     
   - MySQL credentials: Open the `app.py` file and replace the parameters `host`, `user` and `password` of SongsDatabase with your own database credentials.
  
   - Turn on MySQL server

4. Run the application:

   ```bash
   python app.py
   ```

## Usage

1. When prompted, enter the number of songs you want to retrieve from Spotify for each request (Limit of 50).

2. The application will create the database and table if they don't already exist.

3. Songs will be retrieved from Spotify and added to the database. If a song already exists in the database, it will be skipped.

4. The application will print the songs added to the database and send them to the configured Telegram chat using the Telegram bot.

5. If no new songs are found, a message will be displayed indicating that.

## Contributing

Contributions are welcome! If you have any suggestions or improvements, please submit a pull request.

## License

This project is licensed under the [MIT License](LICENSE).

## Contact

For any questions or issues, please contact [lsascol01l@gmail.com](mailto:lsascol01l@gmail.com).
