# Template: template-docs

This template provides a boilerplate repository
for building new docs repositories.


## How to use it

### 1. Fork this repository

Use the fork button in the top-right corner of the github page to fork this template repository. If you are building a repository that belongs inside the Duckietown organization, skip this step. 


### 2. Create a new repository

Create a new repository on github.com while
specifying the newly forked template repository as
a template for your new repository.


### 3. Clone the repo 

Add the `--recurse-submodules` option to automatically recurse the submodules. 


### 4. Add your content

Place your content in the directory `/book` of
your new repository.

For information about how to format the content see the [Duckumentation documentation](https://docs.duckietown.org/daffy/duckumentation/out/index.html)

### 5. Build your book

    $ dts docs build
    
### 6. View the output

If there are no errors, open the file `duckuments-dist/template/out/index.html` in the browser to see your book. 

### 7. Push the updates
