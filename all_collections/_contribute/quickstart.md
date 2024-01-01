---
---

# Quickstart

<div id="toc" markdown="1">
<b>Contents</b>
* TOC
{: toc}
</div>

This quickstart guide will walk you through how to edit existing pages on the Nameless wiki. 

For new contributors, it's best to start with editing your character's page! If your character doesn't already have a page, [open an issue](issues#create-an-issue) and we will make you one ASAP.

# Access the Files

Ask Parker or Vinnie for an invite to the BitD-Philly GitHub organization. You will receive an email with an invite link to the BitD-Philly repository. This is a prerequisite for being able to edit files!

The files used to build the website are located in the Github repository here: [http://github.com/bitd-philly/bitd-philly.github.io](http://github.com/bitd-philly/bitd-philly.github.io).
   
# Edit an existing page
1. Navigate to the [bitd-philly.github.io](http://github.com/bitd-philly/bitd-philly.github.io) repository in the BitD-Philly Github Organization.
2. Switch to the `content` branch.
   ![]({{page.img_root}}quickstart/select-content-branch.png)
3. Click the `all_collections` folder. This folder will contain all the wiki pages that are sorted into various collections. The collections that contain wiki content are `_player_characters`, `_npcs`, `_factions`, and `_locations`. (More may be added later!)
   ![]({{page.img_root}}quickstart/content-branch-files.png)
4. Navigate to the collection page you want to edit. If you're just starting out, find your character page! It will be in the `all_collections/_player_characters` folder. If your character sheet is not there, [open an issue](issues#create-an-issue) and a more experienced contributor will set one up for you!
5. Click the pencil icon to open the editing interface.   
![]({{page.img_root}}quickstart/edit-pc-page.png)
6. Make changes to the file.   
   ![]({{page.img_root}}quickstart/character-sheet-template.png)   
   When first editing, it's adviseable to not edit anything marked as "required" in the "front matter" (the text between the dashed lines at the top of the file). This part of the page is *metadata* that is used to build your character page and reference your character in different places across the entire website!


## Save Changes

1. Click the green "Commit changes..." button.
   ![]({{page.img_root}}quickstart/commit-changes-button.png)
2. Sign off on the commit, adding an extended description if desired.
   ![]({{page.img_root}}quickstart/commit-changes.png)   
3. Click "Sign off and commit changes".
4. Continue editing, committing changes as needed.
   
Note that these changes will not reflect in the website immediately. You can think of commits as "saving" your changes, but they will not be "published" until you or another contributor creates a *pull request* to merge your changes into the website code.

# Publish Changes

## Submit Pull Request 

1. When you see this banner when on the `content` branch, it means there are outstanding changes that can be published.
2. Click "Contribute > Open Pull Request".
   ![]({{page.img_root}}quickstart/pr-banner.png)
3. Ensure the top bar looks like this:
   ![]({{page.img_root}}quickstart/compare-banner.png)
   Specifically, it should read:
   * "base: gh-pages" in the left dropdown
   * "compare: content" in the right dropdown
   * "Able to merge." with a check mark.
4. Add a title and click "Create Pull Request".
   ![]({{page.img_root}}quickstart/start-pr.png)
5. You should see a page that looks like this:
   ![]({{page.img_root}}quickstart/saved-pr-page.png)
6. Wait for your edits to be approved by another contributor to the BitD wiki.

Generally, the reviewer should also merge the pull request once the changes are approved. If they do not, you can follow the next steps to initiate the publishing process yourself.

## Merge Pull Request 
1. Click the arrow next to "Merge Pull Request" to ensure "Create a merge commit" is selected. 
 
   ![]({{page.img_root}}quickstart/select-merge-commit.png)
2. Click the **Merge pull request** button.
3. Click **Confirm Merge**.
   ![]({{page.img_root}}quickstart/confirm-merge-button.png)

Congratulations! Your changes will be published to the website after about 2-3 minutes.