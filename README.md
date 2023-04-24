import os
import shutil

# Specify the directory to be organized
folder_path = "C:/Users/User/Documents"

# Loop through each file in the directory
for filename in os.listdir(folder_path):
    # Get the file extension
    extension = os.path.splitext(filename)[1][1:].strip().lower()

    # Create the directory for the file type, if it doesn't exist
    if not os.path.exists(os.path.join(folder_path, extension)):
        os.mkdir(os.path.join(folder_path, extension))

    # Move the file to the directory for its file type
    shutil.move(os.path.join(folder_path, filename), os.path.join(folder_path, extension, filename))
