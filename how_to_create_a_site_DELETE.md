---
layout: default
title: Create a Site
description: SCDS Do More with Digital Scholarship workshop series
nav_order: 101
---

# How to Create a Workshop Site!
Follow these steps to create a new workshop website from this template repository.

<details markdown="block">
  <summary>
    Table of Contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

## 0. Example Workshop Website

[Example workshop website](https://multipixels.github.io/github-pages-temporary/){: .btn .btn-outline }  

[Example workshop website repository](https://github.com/scds/github-pages/tree/main){: .btn .btn-outline }

## 1. Create a new repository using this template
1. Navigate to the [SCDS template repository](https://github.com/scds/scds-template)
2. Above the file list, click `Use this template > Create New Repository`
3. Select scds as the repository owner 
4. Give the new repository a name (we try to keep it to a few words and use hyphens to delimit words--e.g. *intro-voyant*)
  - Set the description to: `Repository for workshop website: <<WORKSHOP NAME>>`
5. Set the repository visibility to **Public**
6. Click **Create repository from template**
- Full instructions (from GitHub) [here](https://docs.github.com/en/free-pro-team@latest/github/creating-cloning-and-archiving-repositories/creating-a-repository-from-a-template#creating-a-repository-from-a-template).

## 2. Configure GitHub Pages
1. In the new repository, go to **Settings**
2. On the left hand side, select **Pages** (it should be the last item in the **Code and automation** category)
3. Under **Build and deployment**, switch the **None** branch to **main**/**master**
4. Click save. The URL to your new website will be displayed. It will take the form ```https://scds.github.io/<repository_name>```, where ```<repository_name>``` is the name you created in step 4 of the previous section. 

## 3. Set up Google Analytics
1. Go to the [admin page](https://analytics.google.com/analytics/web/#/a2574088p251711101/admin) for the SCDS workshop pages
    - If you do not have access, let Jay know. Skip this step for now and come back to it when possible.
2. Click Data Streams
3. Click **Add Stream > Web**
4. Enter the GitHub Pages URL created in previous section (i.e. ```https://scds.github.io/<repository_name>```). Provide a name.

## 4. Edit the README file 
1. Enter the workshop name, workshop URL, and contributor name(s) where prompted
2. Remove the \<\< \>\>

## 5. Add necessary documents, images, and data  

{: .no_toc }
### assets/docs/
- Add any PDFs (slides, worksheets, etc.) that you will either embed or link to in the main text.

{: .no_toc }
### assets/img/
- Add any workshop-specific image(s), including the title image and any images to be shown in the main content.

{: .no_toc }
### data/
- Add any datasets or other files that are required for the workshop.
  
## 6. Edit the config.yml file 

{: .warning-title }
> Comments
>
> Everything after a **#** is a comment. Comments are ignored by the website.  
> To uncomment a line, remove the **#** at the start.  
> To comment a line, add a **#** at the start.

1. Update/verify lines above "Edit Above" text. Put text in double quotes. These include the following variables:
    - **title** - workshop title
        - If the workshop title is long, try to shorten it. Use acronyms or exclude parts of the title. 
        - Try to keep it shorter than "GitHub and GitHub Pages".
    - **github_repo_url** - GitHub Pages URL from Section 2
    - **gh_edit_repository** - GitHub repository URL from Section 1
    - **ga_tracking** - Measurement ID from GoogleAnalytics from Section 3

    {: .note-title }
    > Example
    >
    > ````yaml
    > title: GitHub and GitHub Pages # Enter workshop title here  
    > github_repo_url: "https://scds.github.io/github-pages/" # Enter workshop URL (in github pages) here  
    > gh_edit_repository: "https://github.com/scds/github-pages" # Enter the github URL for your repo  
    > ga_tracking: G-F9JFEFZ01G # This needs to be set up in Google Analytics once you know the website URL (ask Jay to do this). Then the tracking code needs to be taken from Google Analytics and pasted here.  
    > ````


2. Series specific settings
    - **DMDS** - The SCDS template should already have these settings. An example is included below. <br>

    {: .note-title }
    > Example
    >
    > ````yaml
    > # DMDS Settings
    > subtitle: "This workshop is part of the SCDS Do More with Digital Scholarship series."
    > nav_footer_logo_bottom: "https://raw.githubusercontent.com/scds/jtd-mcmaster/main/assets/images/scds-logo.png"
    > nav_footer_logo_bottom_href: "https://scds.ca/"
    > nav_footer_logo_top: ""
    > nav_footer_logo_top_href: ""
    > ````

    - **DASH** - Comment out the lines under DMDS (add a # symbol at the start of each line), and uncomment the lines under DASH (remove the # symbol at the start of each line).

    {: .note-title }
    > Example
    >
    > ````yaml
    > # DASH Settings
    > subtitle: 'This workshop is part of the Data Analysis Support Hub series.'
    > nav_footer_logo_bottom: "https://raw.githubusercontent.com/scds/jtd-mcmaster/main/assets/images/scds-logo.png"
    > nav_footer_logo_bottom_href: "https://scds.ca/"
    > nav_footer_logo_top: "https://raw.githubusercontent.com/scds/jtd-mcmaster/main/assets/images/dash-logo.png"
    > nav_footer_logo_top_href: "https://library.mcmaster.ca/services/dash"
    > ````

    - **Other/Custom** - Want to make a module that isn't part of DMDS or DASH? Comment out the lines under DMDS (add a # symbol at the start of each line), and uncomment the lines under OTHER (remove the # symbol at the start of each line).
        - **nav_footer_logo_bottom**: Replace this with your series logo link. Leaving it as "" will show no logo.
            - Go to the [assets/images](https://github.com/scds/jtd-mcmaster/tree/main/assets/images) directory in the theme and open your logo. If it isn't there, upload it there. Open the image (on the GitHub website), right click it and click "Copy image address". Use this address.
            - It should look like this: <https://raw.githubusercontent.com/scds/jtd-mcmaster/main/assets/images/scds-logo.png>
        - **nav_footer_logo_bottom_href**: If your series has a dedicated website, put your website link here. This will let users click on the image to go to your website.
        - **nav_footer_logo_top**: An optional, secondary logo. 
        - **nav_footer_logo_top_ref**: Link address for your secondary logo.
        - **subtitle**: A short line attributing the workshop to your series. This appears in the footer of all pages.

## 7. Add content to workshop pages 
There are two places to find content.

### Root directory

This is the top page of your GitHub Repository. It contains most of the template pages.

{: .no_toc }
#### index.md
- This is the home page of your site.
- Edit all the blanks, which include:
    - the page header
    - the link to the title image 
    - the brief description of the workshop
    - the prerequisites (if any)
    - the learning objectives 
    - the duration (if possible)

{: .no_toc }
#### previousOffering.md
- Does your workshop have a live recording you'd still like to feature? This is just the page for that!
- You can include any slides or workshop videos here, alongside the month/year they were used in.
- If you're not using this file, delete `previousOffering.md`. Also, go to `index.md` and set `has_children` at the top to `false` too.

{: .no_toc }
#### preparation.md
- Some workshops may need attendees to install software, create accounts, or download files before attending/starting the workshop. This is where you outline the requirements and/or steps for any preparation needed prior to the workshop. If there is nothing to prepare, mention it on the page.
- Edit:
    - are there any accounts needed?
    - are there any files needed?
    - are there any software applications needed?

{: .no_toc }
#### introduction.md
- Some workshops may have an introduction to the content before diving in. This is where you'll put it.
- Since not all workshops need this page, feel free to remove it.
- Edit:
    - the page header
    - the introductory paragraph
    - video iframe (if applicable)
    - slides/content iframe/links (if applicable)
    - text version (if applicable)

{: .no_toc }
#### lessonsPage.md / workshopRecording.md
- If your workshop has lessons, delete `_workshopRecording.md`. Leave `lessonPage.md` the way it is.
    - If you want to include content in `lessonsPage.md` rather than leaving it as a folder, set `blank` to `true` in the front matter at the top.
- If your workshop has a singular recording/slides, rename `_workshopRecording.md` to `workshopRecording.md` and delete `lessonsPage.md`. Also delete the `lessons/` folder.
    - Edit the link for workshop recording and slides. Remove/add other content as you need.

{: .no_toc }
#### conclusion.md
- This is where you wrap up the workshop. Remind the attendees what they did/learned, any key points to remember, and point them to additional resources.
- Edit:
    - the learning objectives
    - the additional resources

### Lessons Directory

{: .warning}
> If you only have a workshop recording and haven't already, delete the `lessons/` folder and skip this step.

This is where any lessons you create go. 

Make sure all the lessons are ordered right and set parent to "Lessons".

There are already a couple premade lesson pages, including a lesson page with sublesson pages. Use these as examples. Duplicate/delete lessons as you see fit.

Edit:
- the brief description
- the learning objectives
- the lesson video (if applicable)
- the lesson slides/resources (if applicable)
- the text (if applicable)
- the keypoints/summary
- the additional resources (if applicable)

## 8. Final Check and Touchups

- Make sure all the previous/next page buttons work!
  - If they're broken, double check the `nav_order`. Avoid using the same number for two pages.
  - Children pages start back at 1.
  - Tip: If you need to add a new page between 1 and 2, you can use decimals (like 1.5).

{: .note-title }
> Example
> - 1
> - 1.5
> - 2
>     - 1
>     - 2
>     - 3
>         - 1
>         - 2
>     - 4
> - 3

- Delete the `kitchen_sink_DELETE.md`, `common_elements_DELETE.md`, and `how_to_create_a_site_DELETE.md` files.
    - Delete `_workshopRecording.md` if you didn't use it.
    - Delete `lessonsPage.md` and `lessons/` if you didn't use them.
- Delete any pages, images, and files you didn't use.
- Set up Google Analytics.

# Congratulations!

Your website should be up and ready to be used 😊.