Git some basics:

## When you add the a file to git, it does:

1. Create a blob file in .git/objects/ directory and this file contains the compressed content of data/letters.txt.
2. Creates the hash of the file(unique identifer is created for a file), and first 2 characters of the hash are directory name and other two file content.
3. So the content of the file ae save now and compresssed content in git repo
4. It also adds the the file to index file


## When you change the existing file

1. It make a new blob file in .git/objects directory and file has compressed new contents of file
2. It updates the index[index file i.e. .git/index file] pointing to new blob.


## When you make a commit

1. It creates a tree graph to represent the content of the version of the porject being commited
2. It create a commit object
3. It points the current branch to new commit object.

### Tree graph:  
 * We record the current state of directory i.e.[that is] we record the location and contetn of every file in project
 * This graph consist of two objects:  blobs and trees
 * Blobs are zipped file content
 * Tree is directory in project



```
	project
		data 
			letters.txt
			numbers.txt  
```
* So while making a commit in project ** Tree object ** will be created for "data" directory in project

* Tree object that records the content of *data* directory    
   
	```
		100664 blob 6yhhgt54rfde34tgfvbhfty67ui8ytgfr letter.txt
		100664 blob 6yh7uy6tgh65tr4hhffi9omfddi8ytgfr numbers.txt
	```
	
* Tree object for *project* directory: 

	040000 tree sdfdsfisdjfsdlkfjljsdlfjsdlfjsdlj data


* This lines records everything need to create the file
	* first part: permission for the file
	* second part: It's a blob/tree
	* third part: zipped content of file
	* fourth part: name of the file
	
### Commit object

* Commit object is just another text file in .git/objects/:
* This file has all the info about the commit


===
####Objects

* All files that you commited into a Git repository, including the commit info are stored as objects in .git/objects/.

* An object is identified by a 40-character-long string – SHA1 hash of the object’s content.

* There are 4 types of objects:
	* blob - stores file content.
	* tree - stores direcotry layouts and filenames.
    * commit - stores commit info and forms the Git commit graph.
    * tag - stores annotated tag.



####References

* A branch, remote branch or a tag (also called lightweight tag) in Git, is just a pointer to an object, usually a commit object.

* They are stored as plain text files in .git/refs/.
**Symbolic References**

* Git has a special kind of reference, called *symbolic reference*. It doesn’t point to an object directly. Instead, it points to another reference.
	* For instance, .git/HEAD is a symbolic reference. It points to the current branch you are working on.
* 

	

####View git tree

* View the commit-id from branch i.e. .git/refs/heads
* To view the tree: git cat-files -p commit-id
* To view content of file: git cat-files -p commit-id








	





