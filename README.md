Task Manager Bot - README
Overview
This project is a simple Telegram bot that allows users to manage their tasks and also sends
random images to cheer them up. The bot can:
Add tasks with specified date and time.
View all tasks.
Delete tasks.
Send a random image to the user when they feel sad.
The bot stores tasks in an SQLite database and accesses images from a folder on Google Drive.
Make sure to configure the necessary paths and API keys before running the bot.

Prerequisites
Before running the bot, make sure you have the following installed:
Python 3.x
Required Python packages: pytelegrambotapi , sqlite3 , os , random
You can install the necessary package for Telegram bots using:
pip install pytelegrambotapi

Setup Instructions
1. Insert Telegram API Key
You need to insert your own Telegram Bot API key in the following line of the code:
bot = telebot.TeleBot('YOUR_TELEGRAM_BOT_API_KEY')
Replace 'YOUR_TELEGRAM_BOT_API_KEY' with the actual API key of your bot.

2. Configure Paths for Photos and Database
Ensure that the paths for the images and database are correctly set:
Images Folder Path:
This should point to a folder where your images are stored. The bot will randomly select
images from this folder when responding to the "I'm feeling sad" button.
Update the path to the correct folder on your Google Drive:
IMAGES_PATH = '/content/drive/MyDrive/Photo/'
Database Path:
This is the path where the SQLite database is stored. It will store tasks added by users.
Update the path to your database file:
conn = sqlite3.connect('/content/drive/MyDrive/tasks.db', check_same_thread=False)
If you are running the bot in Google Colab, make sure Google Drive is mounted:
from google.colab import drive
drive.mount('/content/drive')

3. Run the Bot
Once you have inserted your API key and verified the paths, you can start the bot by running the
Python script. The bot will begin polling for commands from users and responding accordingly.

Bot Commands and Features
/start: Initiates the bot and presents the main menu with options to manage tasks and request
random images.
My tasks: Shows a list of all tasks stored in the database.
Add task: Prompts the user to add a new task, with task text, date, and time.
Delete task: Allows the user to delete a task from the list.
More about the bot: Provides more information about the bot's functionality.
I'm feeling sad: Sends a random image from the specified folder to cheer up the user.

Example Usage
1. Add a Task:
Click "Add task".
Enter the task text, date (YYYY-MM-DD format), and time (HH format).
2. View Tasks:
Click "My tasks" to see a list of all added tasks.
3. Delete a Task:
Click "Delete task" and select the task to remove.
4. Get a Random Image:
Click "I'm feeling sad" to receive a random image from your specified folder.

Troubleshooting
Invalid API Key: Make sure you are using the correct API key for your Telegram bot.
Incorrect Paths: Ensure the paths to your image folder and database are correct and
accessible.
Missing Dependencies: If the bot does not run, ensure you have
installed pytelegrambotapi using pip install pytelegrambotapi .

License
This project is open-source. Feel free to modify and use it for your own Telegram bot projects.

Enjoy using your Task Manager Bot! Let me know if you have any questions or issues.
