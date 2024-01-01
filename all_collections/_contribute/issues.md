---
---

# Issues

<div id="toc" markdown="1">
<b>Contents</b>
* TOC
{: toc}
</div>

One of the easiest ways to contribute to the website & wiki is through Github's "[Issues](https://github.com/BitD-Philly/bitd-philly.github.io/issues)" feature. Here, you can report bugs, flag articles that need updating, or suggest new wiki pages -- basically, it helps us create and maintain a to-do list for the site!

If you're new to editing the wiki, this can be a great place to start contributing requested content. Just filter the issues by the "good first issue" label, or click [here](https://github.com/BitD-Philly/bitd-philly.github.io/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22).



## What's an issue?

Generally, the Issues feature should be used for medium-sized content tasks, and for reporting any usability problems with the site. Issues should also be well-scoped and have very clear "done" condition. 

Some examples of good issues are:

* Site bugs
    * A broken page
    * A page with lots of broken links
    * A broken link you don't know how to fix
    * Visual or layout bugs
* Content
    * A missing character page
    * A missing NPC, faction, or location
    * A stub that should be expanded to a wiki page
    * Content addition to an existing wiki page

## What's not an issue?

Avoid reporting issues that would take you a very short time to fix personally (e.g., 1-2 minutes); instead, just make the changes directly to the `content` branch. Additionally, do not open issues that have vague end conditions, or have a very large scope of work.

Some examples of bad issues are:

* Easily fixable broken links
* Spelling or grammar errors
* Suggestions for website layout or organization
* Addition of a new section to the website

# How-To

## Create an Issue

1. Visit the [Issues home page](https://github.com/BitD-Philly/bitd-philly.github.io/issues).   
2. Click "New Issue". You should see the following screen.    
![Image indicating the locations to add a title, description, labels to the issue, and the location ofthe submit button.]({{page.img_root}}/issues/submit-issue-screen.png) <br /><br />
3. Add a title (1) and description (2).    
***Note:*** Use [templates](#templates) when possible. When an appropriate template is not available, include as much context as possible in the title and description, and take advantage of Markdown formatting to make the request easy to read & understand.
4. Assign labels using the right-side panel (3).
5. Click "Submit New Issue" (4).   
 
## Start Work on an Issue

The <a href="https://docs.github.com/en/issues/tracking-your-work-with-issues/linking-a-pull-request-to-an-issue" target="_blank">best practice</a> when resolving issues is to create a new branch linked to the issue, make changes to that branch, and then create a pull request to merge the changes into the `content` branch.

1. Select an issue from the [Issues home page](https://github.com/BitD-Philly/bitd-philly.github.io/issues).
2. Click **create a branch** under the **Development** tab on the issue's page.   
![Image indicating the location of the Development tab.]({{page.img_root}}/issues/create-issue-branch.png)
3. Make sure **checkout locally** is checked, then click **create branch**.   
![Image showing the git checkout branch dialogue box with the "checkout locally" radio box checked.]({{page.img_root}}/issues/checkout-local.png)
4. Close the pop-up.
5. There should now be a link to the new branch under the **Development** tab.    
![Image indicating the locations of the new issue branch.]({{page.img_root}}/issues/issue-branch-location.png)  
Click on that link. It will take you to the new branch, which is basically a copy of the site you can edit freely without messing up the current site.
6. Find and edit the files you need to change. The exact process and files depend on which issue you are resolving; for more details on how to find and change files, refer to the relevant documentation. Some common ones are:
* Editing Existing Wiki Pages (Beginner)
* Adding Wiki Pages (Intermediate) --- coming soon!
* Adding Page Stubs and Site Data (Intermediate) -- coming soon!
* Layout changes and site generation (Advanced) -- coming soon!

7. [Commit your changes](tutorial-link) to the issue branch as you edit the files. You (and other contributors!) can also add comments to the issue page to ask questions, provide clarification, or debate the merits of certain edits.

## Close an Issue

After all changes needed to resolve the issue are commited, the next step is to update the site content with the new changes. Here's how that works.

1. Create a [pull request](tutorial-link) to merge your issue branch into the `content` branch. On the pull request page, make sure the `content` branch is on the left, and the issue branch is on the right!
![Image showing the pull request screen for merging the issue branch into the content branch. The branch dropdowns are highlighted, with the content branch on the left and the issue branch on the right.]({{page.img_root}}/issues/merge-issue-branch.png)
9. Click **Create pull request**.
10. Click **Merge pull request** on the next page, then **Confirm merge**. This will update the `content` branch with the new changes.
11. Click  **Delete branch** to delete the issue branch. We no longer need the issue branch now that the changes have been merged into the `content` branch.
![Image with a large purple arrow pointing to the the "delete branch" button.]({{page.img_root}}/issues/delete-issue-branch.png)
12. Go back to the issue's page and scroll to the bottom.
13. Select **Close Issue**.
![Image showing the "close issue" button on the issue page.]({{page.img_root}}/issues/close-issue.png)

Congratulations! Your update will be included the next time the `content` branch is merged to the `gh-pages` branch. (If you're feeling ambitious, go ahead and create that pull request yourself.)


# Resources
## Templates

Here are some templates you can use to create issues for common occurrences, such as missing content and/or data, along with links to examples of each.

### Add content to existing page

**Title**: `Add Short Description of [item] to [wiki page]`    
**Labels**: good first issue, additional page content   
**Description:**
{% highlight markdown %}
# Task: Add Short Description

Add a short description of [item] to the [target wiki page] wiki page under the [heading name] heading.

## Resources

Edit page for [target wiki page]: <link to target markdown file in content branch>

{% endhighlight %}

***Examples:*** [here](https://github.com/BitD-Philly/bitd-philly.github.io/issues/34#issue-2061315940)

### Request a new stub


**Title**: `Add [category] stub for [item]`   
**Labels:** add data   
**Description:**
{% highlight markdown %}
# Task: Add new [category] stub

Add a stub for [item] in the [npc | faction | location | event | misc] category.

Data:
```
- name: Item Name
  excerpt: Write a 1-2 sentence description here.
```
{% endhighlight %}

***Examples:*** [here](https://github.com/BitD-Philly/bitd-philly.github.io/issues/35)

### Expand stub to wiki page

**Title:** `Expand [item] stub to wiki page`   
**Labels:** add wiki page
**Description:**
{% highlight markdown %}
# Task: Add wiki page for [item]

Create a wiki page for [stub] in the [npc | faction | location | event ] page collection.

Current stub: <link to landing page with stub>
{%endhighlight%}

***Examples:*** [here](https://github.com/BitD-Philly/bitd-philly.github.io/issues/36)