---
layout: cheat-sheet
title: গিটহাব গিট চিট শীট
byline: গিট হচ্ছে একটি ওপেন সোর্স ড্রিস্ট্রিবিউটেড ভার্শন কন্ট্রোল সিস্টেম যা আপনার ল্যাপটপ বা ডেস্কটপে গিটহাব সুবিধাদি প্রদান করে। এই চিত শীটে সাধারনভাবে ব্যবহৃত গিট কমান্ড লাইনের নির্দেশনা দেওয়া আছে । 
leadingpath: ../../
---

{% capture colOne %}
## ইন্সটল গিট
গিটহাবের রিপোজিটরির  সাধারন অ্যাকশন ও  উন্নত পরিস্থিতিতে জন্য Git এর একটি স্বয়ংক্রিয়ভাবে আপডেট করার কমান্ড লাইন সংস্করণসহ  ডেস্কটপের জন্য গ্রাফিকাল ইউজার ইন্টারফেস সুবিধাযুক্ত ক্লায়েন্ট আছে।

### উইন্ডোজের জন্য গিটহাব
http://windows.github.com

### ম্যাকের জন্য গিটহাব
http://mac.github.com

লিনাক্স ও POSIX সিস্টেমের জন্য গিট অফিশিয়াল Git SCM ওয়েবসাইটে উপলব্ধ।

### সকল প্ল্যাটফরমের জন্য গিটহাব
http://git-scm.com

## টুল কনফিগার করা
সকল লোকাল রিপোজিটরির জন্য টুল কনফিগার করা

```$ git config --global user.name "[name]"```

নাম ঠিক করুন যেটা আপনি কমিট ট্রান্সেকশনের সাথে  সংযুক্ত করতে চান।


```$ git config --global user.email "[email address]"```

ইমেইল ঠিক করুন যেটা আপনি কমিট ট্রান্সেকশনের সাথে  সংযুক্ত করতে চান।


## রিপোজিটরি তৈরি করা
একটি নতুন রিপোসিটোরি শুরু অথবা একটি বিদ্যমান URL থেকে শুরু করুন।


```$ git init [project-name]```

নির্দিষ্ট নাম দিয়ে একটি নতুন  রিপোসিটোরি তৈরি করুন। 


```$ git clone [url]```

একটি প্রকল্প এবং তার সম্পূর্ণ সংস্করণ ইতিহাস ডাউনলোড করুন। 

{% endcapture %}
<div class="col-md-6">
{{ colOne | markdownify }}
</div>


{% capture colTwo %}

## পরিবর্তন করা
সম্পাদনা পর্যালোচনা করুন এবং একটি কমিট ট্রান্সেকসন ক্রাফট করুন।


```$ git status```

সকল ফাইল লিস্ট করুন যা কমিট করা হবে।


```$ git diff```

ফাইলগুলোর পার্থক্য দেখুন যেগুলো এখনো staged হয়নি।


```$ git add [file]```

সংস্করনের  জন্য প্রস্তুতি ফাইল স্ন্যাপশট করুন।


```$ git diff --staged```

staging এবং last file version এরমধ্যে পার্থক্য দেখুন।


```$ git reset [file]```

ফাইল Unstages, কিন্তু তার বিষয়বস্তু অপরিবর্তিত রাখুন।


```$ git commit -m"[descriptive message]"```

ফাইলের  স্ন্যাপশট ভার্শনের ইতিহাসে সংরক্ষন করুন।

## গ্রুপ পরিবর্তন
Name a series of commits and combine completed efforts


```$ git branch```

Lists all local branches in the current repository


```$ git branch [branch-name]```

Creates a new branch


```$ git checkout [branch-name]```

Switches to the specified branch and updates working directory


```$ git merge [branch-name]```

Combines the specified branch’s history into the current branch


```$ git branch -d [branch-name]```

Deletes the specified branch
{% endcapture %}
<div class="col-md-6">
{{ colTwo | markdownify }}
</div>
<div class="clearfix"></div>


{% capture colThree %}
## Refactor file names
Relocate and remove versioned files


```$ git rm [file]```

Deletes the file from the working directory and stages the deletion


```$ git rm --cached [file]```

Removes the file from version control but preserves the file locally


```$ git mv [file-original] [file-renamed]```

Changes the file name and prepare it for commit

## ট্র্যাকিং দমন
Exclude temporary files and paths

```
*.log
build/
temp-*
```

A text file named `.gitignore` suppresses accidental versioning of files and paths matching the specified patterns


```$ git ls-files --others --ignored --exclude-standard```

Lists all ignored files in this project

## ফ্রাগমেন্টস সংরক্ষন
Shelve and restore incomplete changes


```$ git stash```

Temporarily stores all modified tracked files


```$ git stash pop```

Restores the most recently stashed files


```$ git stash list```

Lists all stashed changesets


```$ git stash drop```

Discards the most recently stashed changeset
{% endcapture %}
<div class="col-md-6">
{{ colThree | markdownify }}
</div>

{% capture colFour %}
## হিস্টোরি রিভিউ
Browse and inspect the evolution of project files


```$ git log```

Lists version history for the current branch


```$ git log --follow [file]```

Lists version history for the file, including renames


```$ git diff [first-branch]...[second-branch]```

Shows content differences between two branches


```$ git show [commit]```

Outputs metadata and content changes of the specified commit

## কমিট রিডো করা
Erase mistakes and craft replacement history


```$ git reset [commit]```

Undoes all commits after `[commit]`, preserving changes locally


```$ git reset --hard [commit]```

Discards all history and changes back to the specified commit

## সিঙ্ক্রোনাইজড  পরিবর্তনগুলি
Register a remote (URL) and exchange repository history


```$ git fetch [remote]```

Downloads all history from the remote repository


```$ git merge [remote]/[branch]```

Combines the remote branch into the current local branch


```$ git push [remote] [branch]```

Uploads all local branch commits to GitHub


```$ git pull```

Downloads bookmark history and incorporates changes
{% endcapture %}
<div class="col-md-6">
{{ colFour | markdownify }}
</div>
