## University of Southampton LaTeX template ##


This is a modified template, based on the official template found [here](http://edshare.soton.ac.uk/19374/ "LaTeX Thesis template").
The modifications are detailed below, in the 'Customisation' section.
This is intended to be a universal template that can be used by PhD candidates of any discipline and any department.
At the moment, the university name (*University of Southampton*) is hard-coded inside the LaTeX class.
If you would like to use this template for another university, you will have to modify the `\University` variable in the class file(s).

### Installation ###
The templates are provided in a zip file. 
Two versions of the zip file are available, one for local and one for online installation.
Depending on your workflow, two methods of installing are available:

#### Overleaf installation ####
If you are using [Overleaf](https://www.overleaf.com/ "Overleaf"), simply download the **online-zip** file and upload it straight to Overleaf
(*New project -> Upload project -> Choose zip file*).

#### Local installation ####
If you are working with a local LaTeX installation, you will have to install the template *.tex* files and the accompanying class files
to a directory that is discoverable by your LaTeX packages.     

1. Download the file titled **local-zip** and extract its contents. Usually you will want to extract it to your local `TEXMF` directory.   

2. For Windows installations, the user `TEXMF` directory is usually located at `C:\Documents and Settings\username\My Documents\TeX`.    
For Mac and Linux installations, the path is `/User/username/Library/texmf`.   
     
    You can locate the path of the directory by firing up a terminal (`cmd` window in Windows) and typing:  


          kpsewhich --var-value TEXMFHOME
   


    If the directory doesn't exist, you can create it manually.   

3. Extract the contents of **local-zip** to your `TEXMF` directory. Make sure to maintain the directory structure intact
(if prompted, select to *merge* the contents of the folder rather than *replace* them).   

4. On Windows, click `Start->Programs->MiKTeX->MikTeX Options` and click on "Refresh Now".   
    On Unix/Mac, open a terminal and type:   
    
           texhash ~/texmf   


### Template structure ###
The template contains three class files and a set of *.tex* files to get you started.   

###### The class files are:   

`ecsprogress.cls` -- This style file will produce a document for submission as a first-year/9-month progress report.   
`ecsminithesis.cls` -- This style file produces a document for submission as an 18-month/upgrade report.   
`ecsthesis.cls` -- This style file produces a document for the final submission of the PhD thesis.   



###### Directory structure:
The *.tex* files are located at `templates->latex->ecsdocs`. It is advised to work on copies of these templates;
this way, if you come across any issues, you can revert back to a clean copy. Copy the whole directory structure from
`ecsdocs` into a different location and start working there. The directory structure of `ecsdocs` is this:   

          ecsdocs  --> Appendices   
                                    '--> AppendixA.tex   #An appendix file
                  '--> Bibliography 
                                    '--> biblio.bib   #The bibliography file containing bibliographic references
                  '--> Chapter1 
                                    '--> Chapter1.tex   #Sample of a chapter
                  '--> Images 
                                    '--> figure.eps   #Sample picture in *.eps* format
                                    '--> figure.pdf   #Sample picture in *.pdf* format
                  '--> Introduction 
                                    '--> Introduction.tex   #Sample introductory chapter
                  '--> main 
                                    '--> Progress.tex   # The main file. Use this to compile the whole document.
                  '--> Preable 
                                    '--> Abstract.tex   #The abstract
                                    '--> Info.tex      #All customisation options are contained here
                                    '--> Preamble.tex   #File containing extra commands and instructions for LaTeX. Any additional packages you want to include can go there.   
 


### Customisation ###
The fields that require you to customise them are indicated in the *.tex* files by a `%TODO` comment. In most editors, these
comments will appear highlighted.   


Most of these fields are within the *Info.tex* document:   

- Information for the cover and abstract page:   
    `\dept` -- Your University department name   
    `\fact` -- The faculty of your department   
    `\grp` -- Your research group (leave blank if non-applicable)   
   
    `\title` -- The title of your project   
    `\authors` -- Your name   
    
    `\supervisor` -- The name of your supervisor(s) (Add more lines as needed. Remember to end each line with `\\`)   
    `\examiner` -- The name of your supervisor(s) (Add more lines as needed. Remember to end each line with `\\`)   

     `\addresses` -- Do not modify   
     `\date` -- Will produce the date of the last compilation. Change if you require a specific date.   
     `\subject` -- Any categories you wish printed underneath the title   
     `\keywords` -- Any keywords you want embedded in the resulting pdf   

- Information about the citation style:   
    `style=` refers to the format of the bibliography at the end of the document. Uncomment your preferred style as needed.   
    `citestyle=` refers to the format of the citations in text. Uncomment your preferred style.   

- Information about the bibliography sources:
    `\addbibresource` The default is *biblio.bib*. You can change this to use a different file, or add extra `\addbibresource`
    underneath, in case you're using more than one *.bib* files.   
    
- Information about the font type:   
    Uncomment the following lines in case you'd like to modify the font used by the document:   
    `%\renewcommand{\sfdefault}{phv}  %<---- To change the default font`   
    `%\renewcommand{\familydefault}{\sfdefault}`    

- Information about the colour of the cover and abstract:
    `\defaultcolour` -- Uncomment one of the available colours to change how the links (names, faculty, departments etc.) appear.
    Applies to the cover, abstract and declaration only.   
    

In the *Progress.tex* document:   

You can enter acknowledgments into `\acknowledgements{ }` and a dedication in `\dedicatory{ }`. If you don't want these
section to appear, you will have to comment them out.   
The `\authorshipdeclaration{}` takes no argument. It only produces a declaration page if you are using the `ecsthesis` class.   

The abbreviations list has been substituted by the `nomencl` package. To define abbreviations in your text use:   

            \nom{ABRV.}{Explanation}   
          
For example, `\nom{ID}{Identification}` will produce an entry:    

            Abbreviations   
            --------------
            
              ID            Identification    


Your content goes after `\mainmatter`. 
All chapters are organised into subfiles.
Create additional *subfiles* as needed,
but makesure to maintain the correct structure:   
          % !TeX root = Name-of-the-subfile.tex
          
          \documentclass[../main/Progress.tex]{subfiles}
          \begin{document}
              ...some content here
          \end{document}   
          
 Normally, auto-complete won't be provided for citation commands when used in a subfile. 
 To circumvent this, declare your *bib* file again inside your subfile (`\addbibresource{}`) and refresh.
 This will ensure that autocomplete gets populated.
 However, make sure to comment out that line before you compile your master document.   
 
 
    
    
    
    
 ## Have fun! ##
 &copy; 2019 Niko Tsakalakis - These templates are distributed under a [CC BY-NC-ND](https://creativecommons.org/licenses/by-nc-nd/2.0/uk/) licence.
 Please use responsibly. 





