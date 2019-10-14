*readme.txt*                         rename files in bulk with posh_bulkrename

                                 ┌─┐┌─┐┌─┐┬ ┬                                ~
                                 ├─┘│ │└─┐├─┤                                ~
                                 ┴  └─┘└─┘┴ ┴                                ~
                        ┌┐ ┬ ┬┬  ┬┌─┬─┐┌─┐┌┐┌┌─┐┌┬┐┌─┐                       ~
                        ├┴┐│ ││  ├┴┐├┬┘├┤ │││├─┤│││├┤                        ~
                        └─┘└─┘┴─┘┴ ┴┴└─└─┘┘└┘┴ ┴┴ ┴└─┘                       ~
                                                                             ~
==============================================================================
CONTENTS                                                    *NERDTree-contents*

    1.Intro...................................|posh_bulkrename|
    2.Usage...................................|posh_bulkrenameUsage|
    3.Features/Options........................|posh_bulkrenameFeatures|
        3.1.Editor............................|posh_bulkrenameEditor|
        3.2.EditorArgs........................|posh_bulkrenameEditorArgs|
        3.3.Pattern...........................|posh_bulkrenamePattern|
        3.4.Attrs.............................|posh_bulkrenameAttrs|
    4.DefaultEditor...........................|posh_bulkrenameDefaultEditor|

==============================================================================
1. Intro                                                      *posh_bulkrename*

Posh? Bulkrename? What is this??

    * Posh = Powershell
    * Bulkrename = renaming bunch of files at once

Posh_bulkrename is a simple utility module which can help you mass rename
bunch of files with your favorite text editor and since there are already a
lot of powerfull texteditors with really good text manipulation abilities that
are more than capable for editing a list of filenames, so downloading a heavy
or bloaty program for such a simple task when you already have such powerful
texteditors is atrocious. So this simple utility helps you accomplish this
simple problem with tools that most likely you already have. 

==============================================================================
2. Usage                                                 *posh_bulkrenameUsage*

Using posh_bulkrename is really easy
    
    * first step is to import posh_bulkrename in your powershell $PROFILE by
      writing the following line in your profile: >

      Import-Module path\to\posh_bulkrename.psm1
<

That's it, the module has been imported, now to use it, just go into the
directory with the files you want to bulkrename and open powershell in that
directory and write: >

    bulkrename
<

a window of notepad with all the filenames in the current directory will be
opened, you can change the filenames that you want to rename and after saving
and closing it, all the changed filenames will automatically be renamed.

==============================================================================
3. Features/options                                   *posh_bulkrenameFeatures*

Selections of editor, supplying optional arguments to the specified editor and 
filtering files with pattern and attributes, will be discussed in this
section.

------------------------------------------------------------------------------
3.1. Editor                                             *posh_bulkrenameEditor*

it is possible to specify editor to be used with bulkrename with -editor flag
example: >
    bulkrename -editor vim
<

------------------------------------------------------------------------------
3.2. EditorArgs                                     *posh_bulkrenameEditorArgs*

To supply optional arguments to editor selected one can easily supply them by
-editorArgs flag and supplying powershell array, example: >
    bulkrename -editor vim -editorArgs "-u","NONE"
<

------------------------------------------------------------------------------
3.3. Pattern                                           *posh_bulkrenamePattern*

It is also possible to filter the files to be bulkrenamed by mentioning a
pattern with -pattern flag, example: >
    bulkrename -pattern "*.txt"
<

It is also possible to specify a directory with pattern flag, examples: >
    bulkrename -pattern "c:\games"
    bulkrename -pattern "c:\games\*.txt"
<

------------------------------------------------------------------------------
3.4. Attributes                                          *posh_bulkrenameAttrs*

To further filter the filenames to be renamed one can do so by specifying file
attributes with -attrs flag. 
NOTE: most of the powershell file attributes can be used.

example: >
    bulkrename -attrs "d"
    bulkrename -attrs "d","a"
    bulkrename -attrs "r"
<

NOTE: without attrs flag filenames of all attributes are included except
filenames with system and hidden attributes.

To select files having any of the the powershell attributes (files with system
files are still excluded) do: >
    bulkrename -attrs "all"
>

==============================================================================
4. DefaultEditor                                 *posh_bulkrenameDefaultEditor*

If no editor is selected with -editor flag notepad is used because its
available on all windows machines for which this utility is meant for 

but if you want to change the default editor to be used when just invoking the
"bulkrename" command in a directory, you can easily do so by setting an
environmental variable called "EDITOR" (without quotes) with your favorite
text editor as its value. 







