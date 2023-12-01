# back up entire folder structure
tar -csvpzf backup.folderName.tar.gz folderName

# log the back up created
# add the date, time and file name to file. Must create file first
echo "date, time, fileName" | sudo tee folderName/fileName

# display the content of the file
cat SharedFolders/backups.csv