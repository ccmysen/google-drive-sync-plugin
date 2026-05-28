# Google Drive Sync with Edits

Google Drive Sync with Edits is a seamless, secure, and mobile-friendly plugin that synchronizes your Obsidian vault notes and assets with Google Drive. It operates automatically in the background to ensure your notes are backed up and accessible across all your devices and allows for manual edits including edits directly in google drive.

---

## Key Features

* **Two-Way Synchronization**: Automatically reconciles changes between your local Obsidian vault and Google Drive.
* **Real-Time Incremental Sync**: Edits, creations, renames, and deletions are detected in real-time and pushed to Google Drive (with a 5-second debounce delay to prevent rate-limiting while typing).
* **Secure and Private (App-Specific Access)**: The plugin **only** has access to folders and files it creates. It cannot view, edit, or delete any of your other personal files on Google Drive.
* **Visual Pending-Sync Indicators**:
  * An asterisk (`*`) is appended to the note header title when a file has unsaved edits waiting in the sync queue.
  * An hourglass (`⏳`) is appended next to the file name in the File Explorer to indicate it has pending changes.
* **Conflict Resolution**:
  * **Text Files**: Conflicting edits on the same file are merged inline using Git-style conflict markers (`<<<<<<< Local Changes` and `>>>>>>> Remote Changes`), ensuring no data is lost.
  * **Binary Files**: If a binary file (e.g. images, PDFs) has conflicting edits, the local file is renamed with a `.sync-conflict` prefix, preserving both versions.

---

## Getting Started & Configuration

After installing and enabling the plugin, go to **Obsidian Settings** → **Google Drive Sync with Edits** to configure your connection:

### 1. Authentication
Click **Login** to authorize the plugin to access your Google Drive. There are two modes available:
* **Automatic (Default)**: Redirects you to a secure login page and automatically deep-links back to Obsidian to complete authorization.
* **Manual Authentication**: If your device restricts custom deep links (common on some mobile/isolated systems), enable **Manual Authentication** in settings. You can then copy the authorization code from your browser and paste it directly into Obsidian.

### 2. Synchronization Settings
* **Destination Folder Name**: Specify the name of the folder on Google Drive to sync with (defaults to your vault's name). You can also set this to `root` to sync your vault directly to the main Google Drive directory.
* **Sync Interval (Minutes)**: Configures how often a full, bidirectional sync runs automatically in the background (default is `15` minutes). Set this to `0` to disable periodic full syncs.

---

## How to Use

Once configured, the plugin runs entirely in the background. 

* **Auto Sync**: Pushes your changes automatically as you edit notes, and pulls remote changes periodically.
* **Editor/File Explorer Shortcuts**:
  * Right-click inside any editor or on a file in the File Explorer and select **Force Google Drive sync** to run a manual, immediate full sync.
  * Right-click and select **Prune empty local folders** to clean up empty folders in your vault.
