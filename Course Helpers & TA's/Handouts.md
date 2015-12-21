# Introduction

All handouts are stored in this GitHub repo [github.com/learnable-content/Course-Handouts](https://github.com/learnable-content/Course-Handouts). Each course has a separate branch and employs the following structure:

* `README.md` - an index file listing all lessons.
* `<course_name>_handouts` - directory containing all handout materials in both `.md` and `.pdf` formats.
    * `lesson<x-y>.md` and `lesson<x-y>.pdf` - handout for the particular lesson.
    * `headings` - directory containing heading images. Heading image consists of course's title, author's name and Sitepoint's logo.

Example of course's index:

![](https://trello-attachments.s3.amazonaws.com/55548f698bfa489a97140ea1/805x553/54b22dec7c0eeea17586d0e903b55e7a/example_of_course_index.png)

Example of a heading:

![](https://trello-attachments.s3.amazonaws.com/55548f698bfa489a97140ea1/1031x727/d43ba6ba83b30fb1db89413d4c903386/example_of_heading.png)

# Creating a New Branch

If you hadn't already done so, clone the repo on your PC.

```
git clone https://github.com/learnable-content/Course-Handouts.git
```

Create a new branch named after the course and checkout there from the `master` branch (make sure that you are on `master`!):

```
git checkout master
git checkout -b course_name_goes_here
```

Inside the root directory of the cloned repo create a folder named after the course plus `_handouts`, for example `Introduction_to_Git_handouts`. Place all handouts in that directory.

# Creating Handouts

Inside the `handouts` folder create a new markdown file (with the `.md` extension). File's name has to contain lesson and step number (divided with `-` or `.`) that this handout belongs to. It's also recommended to provide the "lesson" word in the title. Example of valid file names:

* `lesson1-1.md`
* `2.2lesson.md`

Open markdown file for editing. MarkdownPad ([markdownpad.com](http://www.markdownpad.com)) is the recommended editor, but you can stick with any other option.

Copy lesson's transcript into the file. Transcript can be found in the "Transcript" tab right under the video on Sitepoint Premium.

![Transcript](https://trello-attachments.s3.amazonaws.com/54b8563f78d5118ad2a4ef74/876x757/de4e4fc135a632a90904220ce8f27624/transcript_tab.png)

# Editing Handouts

Begin editing the handout. All formatting should be done with [markdown](https://daringfireball.net/projects/markdown/) (when using MarkdownPad, [GitHub-flavored Markdown](https://help.github.com/articles/github-flavored-markdown/) is the preferred option).

![](https://trello-attachments.s3.amazonaws.com/5552df8a951e335dd8aed5a9/913x488/dfb5f194da8fd797ebc993241cf3abb8/markdown_formatted.png)

Some guidelines:

* Handout's structure should strictly follow transcript.
* All headers should be retained, but formatted as headers in markdown (with `#` symbols).
* Re-write long sentences, remove unneeded words used in spoken language, compile multiple sentences into one when possible (by extracting the main idea). Divide long paragraphs into short ones. Handouts should be concise and easy to follow.
* Provide code examples. If some code is mentioned in the text, it has to be present below. Format the code with markdown as well using proper indentations.
* Provide screenshots if necessary. For example, if the lesson is about the usage of some complex GUI, screenshots are required. Place screenshots into a nested folder named `imgs` or `screenshots`, for example.
* Format links with markdown as well to make them clickable.
* In most cases the Conclusion (or Summary) section is not necessary and can be removed.

After finishing working with handouts, add heading images to each file.

1. Create a nested folder named `headings` and place all heading images there.
2. File names should contain lesson and step number divided with `-` or `.` (just like handout files' names).

You can then edit each file manually to include headings and then generate an index, or use LessonsIndexer program which is recommended. However, it requires some additional setup and you can refer to its documentation [here](https://github.com/bodrovis/lessons_indexer).

When using LessonsIndexer, execute the following command to add headings and generate course's index:

```
lessons_indexer -p WORKING_DIR -i -d HEADINGS_DIR
```

`WORKING_DIR` - absolute (full) path to the root directory of the cloned GitHub repo that contains the nested `_handouts` directory.

`HEADINGS_DIR` - relative path (for example, `headings`) to the directory containing heading images.

This command will append heading images to the beginning of each handout and generate course's index in the `README.md` file located in the root of a working dir. Please note, that if `README.md` is already present there, **all its contents will be erased**. You can specify another output file instead by using the `-o` flag. Read LessonsIndexer's docs for more info.

When creating the index file manually, use the following structure:

```md
# Index for the Getting Started With Backbone JS course

* [Lesson 1-1](Getting_Started_with_Backbone_JS_handouts/lesson1-1.md)
* [Lesson 1-2](Getting_Started_with_Backbone_JS_handouts/lesson1-2.md)
* [Lesson 1-3](Getting_Started_with_Backbone_JS_handouts/lesson1-3.md)
```

# Generating PDF files

After creating handouts in `.md` format, generate the corresponding `.pdf` files. Once again, you may either use LessonsIndexer or MarkdownPad (or any other program) to do it manually. Please note, that LessonsIndexer requires Pandoc and LaTex to be installed for this functionality to work. Read more [here](https://github.com/bodrovis/lessons_indexer#pdf-generation).

To generate PDFs for each handout, use the following command:

```
lessons_indexer -p WORKING_DIR -f -s
```

This process may take a couple of minutes (about 5-10 seconds per file).

# Pushing to GitHub

You can either push the newly created branch to GitHub manually or by using LessonsIndexer (which is easier). Here is the relevant command for the LessonsIndexer:

```
lessons_indexer -p WORKING_DIR -s -g -m MESSAGE
```

`WORKING_DIR` - absolute path to the root directory of the cloned repo.

`-m` is optional, it allows to set the commit message.

![](https://trello-attachments.s3.amazonaws.com/555494b2d9fd3b38c5ad30b3/787x487/0fba56796d83ab102c2d537abe9ee287/branches_with_courses.png)