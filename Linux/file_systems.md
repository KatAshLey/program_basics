# check directory
pwd

# change directory
cd folderName

# make new folder
mkdir folderNames(can list multiples)

# list what is in current folder, can also list other folder by ls folderName
ls

# create empty files
touch fileName

# change folder up one level then into folder
cd ../folderName

# to create empty files in a folder
touch folderName/fileName

# validate all files and folders in parent folder
ls -laR

# to copy a folder
cp -r folderName copyToLocation

# remove empty directory/folder
rmdir folderName

# to remove folder and files, can do multiple files but must use folderName/fileName for each
rm folderName/fileName

# move folder location. 
mv folderName toMovedLocation

# verify folder move
ls . movedFolderLocation/folderThatWasMoved

# move files, can list multiple files. mv ../backup.CompanyA.tar.gz IA/
mv fileName folderName

