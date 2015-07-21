import os
import shutil

# list all directories in current directory and put them into an array for each

dirs = []

for x in range(0, len(os.listdir('.'))):
    if os.path.isdir(os.listdir('.')[x]):
    	dirs.append([os.listdir('.')[x]])

print dirs

# find the numbers in the strings of the names for directories and print number in dirs

for x in range(0, len(dirs)):
	# print dirs[x][0].split('_EP')[1]
	dirs[x].append(dirs[x][0].split('_EP_')[1])

# print dirs

# list all files throw out .dsstore and the script file

files = []

for x in range(0, len(os.listdir('.'))):
    if os.path.isdir(os.listdir('.')[x]) == False:
    	if os.listdir('.')[x] == '.DS_Store' or os.listdir('.')[x] == 'script.py' or os.listdir('.')[x] == '._script.py':
    		print 'skipped '+ os.listdir('.')[x]
    	elif '._' in os.listdir('.')[x]:
    		print 'skipped' + os.listdir('.')[x]
    	else:
    		files.append([os.listdir('.')[x]])

# print files

# find the numbers in the strings of the names files

def hasNumbers(inputString):
	return any(char.isdigit() for char in inputString)

def findNumber(fileInput, indexNum):
	for y in range(0,len(fileInput)):
		if fileInput[y].isdigit():

			newNum = fileInput[y]

			# instead of writing 1 then 5 write 15, concat diget strings
			#  dirty as fuck
			for z in range(y+1, len(fileInput)):

				if(fileInput[z].isdigit()):

					newNum = newNum + fileInput[z]

				else:

					files[indexNum].append(newNum)
					return

for x in range(0, len(files)):
	if hasNumbers(files[x][0]):
		findNumber(files[x][0], x)

# print files

# if number of file == number of dir then mv file to folder

def matchFile(indexNum, filePath):
	for y in range(0, len(files)):
		# print "hey"
		# print files[y]
		if(indexNum == files[y][1]):
			# print files[y][0]

			dst = filePath+ files[y][0]

			print dst

			# print dst

			shutil.copyfile(files[y][0], dst )



			rmdst  = "./"+files[y][0]

			print rmdst

			# shutil.move(rmdst, dst)

			os.remove(rmdst)

print len(dirs)

for x in range(0,len(dirs)):

	# print dirs[x]

	dst = './'+dirs[x][0] +'/'
	# print dst
	# print dirs[x][1]
	matchFile(dirs[x][1],dst )

