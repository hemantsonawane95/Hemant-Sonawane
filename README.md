# FolderSync

FolderSync is a one-way folder synchronization tool written in Python. It maintains an exact copy of a source folder in a replica folder by periodically updating the replica to match any changes in the source.

## Features

### One-Way Synchronization
Ensures the replica folder is an exact copy of the source folder. New or updated files are copied, and deleted files are removed.

### Periodic Updates
The synchronization process runs at user-defined intervals, so the replica is always up to date.

### Logging
All operations (copying, updating, and deleting files/directories) are logged both to the console and a specified log file.

### Command-Line Configuration
Users can specify the source and replica folder paths, the sync interval, and the log file path via command-line arguments.

## How It Works

### Scanning the Source Folder
The program traverses the source folder and:
- Creates any missing directories in the replica.
- Copies new files to the replica.
- Compares files using their MD5 hash and size, updating them if they differ.

### Cleaning the Replica Folder
After processing the source folder, the program checks the replica folder and deletes any files or directories that are not present in the source.

### Repeating the Process
This synchronization cycle repeats at the interval specified by the user.

## Installation

### Clone the Repository
```bash
git clone https://github.com/example/FolderSync.git
cd FolderSync
```
## Usage

Run the program from the command line with the following syntax:

```bash
python folder_sync.py --source "/path/to/source" --replica "/path/to/replica" --interval 60 --log "/path/to/logfile.log"
```
```
--source: The path to the source folder.

--replica: The path to the replica folder.

--interval: The time interval in seconds between synchronizations (default is 60 seconds).

--log: The path to the log file where actions will be recorded.
```
