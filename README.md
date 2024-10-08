# Google Drive File Copier in Google Colab
This program was designed to archive Google Drive materials owned by legacy student Google accounts at Northeastern University, but contained within the lab's Google Drive. The script automates the process of copying files and folders from Google Drive into a specified folder in the Colab environment. It handles authentication via OAuth2 and utilizes the Google Drive API to fetch files and directories shared with the user.

## Key Libraries:
- **pydrive.auth**: For user authentication.
- **pydrive.drive**: Provides access to Google Drive files.
- **google.colab.auth**: Authenticates the user in Colab.
- **oauth2client.client**: Handles OAuth2.0 credentials.
- **os**: Interacts with the filesystem for directory creation and file management.

## Steps in the Script:

1. **Authenticate User**: The script authenticates the user using OAuth2 and creates a PyDrive client.
2. **Define Helper Functions**: 
   - `get_existing_items_in_folder(folder_id)`: Retrieves a list of file and folder names in a specified folder.
   - `create_folder(parent_folder_id, folder_name)`: Creates a new folder in Google Drive and returns its ID.
   - `copy_file(file_id, destination_folder_id, existing_files)`: Copies a file to a specified folder, ensuring it hasn’t been copied already.
   - `copy_folder(source_folder_id, destination_folder_id)`: Recursively copies a folder and its contents, avoiding duplication.
3. **Locate Source Folder**: The script searches for the folder titled "NULab and DITI" that is shared with the user.
4. **Create Destination Folder**: It creates a new folder named "Copy of NULab and DITI" in Google Drive, or uses the existing folder if found.
5. **Copy Process**: The script initiates the copying of the source folder and its contents, displaying a summary of successes and failures.


