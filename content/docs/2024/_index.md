---
weight: 1
title: 2024
type: docs
---

# TREC 2024 Lateral Reading Track Guidelines

**Notice: Information on this page is tentative. Please follow our Twitter account [@TREC_LR](https://twitter.com/TREC_LR) or [Google Groups](https://groups.google.com/g/trec-lateral-reading-track) for important announcements and discussions.**

## Overview

Welcome to the TREC 2024 Lateral Reading Track.
In the first year of this track, our goal is to explore NLP and IR technologies to support the tested practice of Lateral Reading during people's trustworthiness evaluation of online news, given the civic importance of trustworthy news and a decline in trust in news over the years [(Brenan, 2022)](https://news.gallup.com/poll/403166/americans-trust-media-remains-near-record-low.aspx).

While directed education on how to do Lateral Reading can be an effective means of helping people better evaluate the trustworthiness of information [(McGrew et al., 2019)](https://bpspsychub.onlinelibrary.wiley.com/doi/abs/10.1111/bjep.12279), this training cannot easily reach the millions of people who use the Internet and are finished with their schooling.
As such, an opportunity exists for systems to assist users with Lateral Reading by helping users understand what they should question about a document and helping them find other documents that can answer those questions.

In the first year, this track has two tasks with separate deadlines. 
For the first task, given a news article, participants need to raise questions to support users in performing Lateral Reading.
The figure below shows some example questions for part of a news article on the left.
After the deadline for Task 1, we will release the questions NIST assessors come up with to participants for the second task, where participants need to retrieve documents from the specified web collection to answer those questions.

<img src="/lr_questions_example.png" alt="Example Questions for Lateral Reading" title="picture_lr_questions_example" style="border-radius: 0"/>

## Data

- **News Articles**: We will select 50 news articles, each about a different event, published in 2021 and 2022 from various sources. 
- **Web Collection**: Task 2 will use the English subset `ClueWeb22-B-English` of the new [ClueWeb22](https://www.lemurproject.org/clueweb22.php/) Category B dataset as the document collection, which contains about 87 million popular web documents of roughly 200 GB data (size of plaintext).
This web collection was collected around February 2022. Please refer to their website for how to obtain the dataset.

Considering the size of `ClueWeb22-B-English`, we suggest you obtain the collection as soon as possible, ideally before the release of questions for Task 2.

## Tasks

As mentioned earlier, we have two tasks with separate submission due dates.

- **Task 1: Question Generation**
    - Given a news article, participants need to generate 10 questions that are useful for people to know when evaluating the trustworthiness of the article.
    - **Provided Input**: <u>50 news articles</u> in plaintext from the data collection.
    - **Expected Output**: <u>10 questions</u> that support Lateral Reading ranked by their importance for each article.
    - After the submission due date of Task 1, we will make available the questions that NIST assessors raise during their evaluation of each news article.
- **Task 2: Document Retrieval**
    - Given a news article and 10 questions raised by NIST assessors, participants need to retrieve 10 documents from the web collection that help answer those questions.
    - **Provided Input**: `ClueWeb22-B-English` and <u>50 news articles (each with 10 questions)</u>.
    - **Expected Output**: <u>Top-10 ranked documents</u> as sources of answer to each question.
        
Since we will provide questions from NIST assessors for Task 2, participating in Task 2 does not require your participation in Task 1.
You can choose to participate in either one or both tracks.

## Tentative Schedule

- **Task 1 Article Release**: Early May
- **Task 1 Question Generation <u>Submission Due</u>**: Late June
- **Task 2 Question Release**: Mid June
- **Task 2 Document Ranking <u>Submission Due</u>**: Late August
- **Result Release**: Late September
- **Notebook <u>Paper Due</u>**: Late October
- **TREC 2024 Conference**: November 18-22 at NIST in Gaithersburg, MD, USA

## Evaluation

NIST assessors will judge the usefulness of generated questions from Task 1 and the usefulness of retrieved documents to answer the corresponding question in the context of the news article from Task 2.
Evaluation details are to be determined.

## Q&A

1. How do we register to participate in this track? \
Please follow the TREC registration guidelines from their [Call for Participation](https://trec.nist.gov/pubs/call2024.html).

## Organizers

<style>
    table {
        width: 100%;
        background-color: white!important;
        border-collapse: collapse; /* Ensures there are no spaces between cell borders */
    }
    th, td {
        padding: 8px; /* Add some padding for content inside cells */
        text-align: left; /* Align text to the left */
    }
    th:first-child, td:first-child {
        max-width: 21%; /* Set minimum width to 21% of the table/page width */
        width: 150px;
    }
    /* Remove borders */
    td, th {
       border: none!important;
    }
    img {
        border-radius: 20%;
    }
</style>

<table>
    <tr>
        <th><img src="https://scholar.googleusercontent.com/citations?view_op=medium_photo&user=Hg46RfsAAAAJ&citpid=7" alt="Dake Zhang" title="picture_dake_zhang"/></th>
        <td><b>Dake Zhang</b> <br> University of Waterloo <br> Waterloo, Ontario, Canada <br> <a href="https://zhangdake.com.cn/">Website</a> &nbsp; <a href="https://www.linkedin.com/in/zhangdake/">LinkedIn</a> &nbsp; <a href="https://twitter.com/ZhangDake1998">Twitter</a></td>
    </tr>
    <tr></tr>
    <tr>
        <td><img src="https://scholar.googleusercontent.com/citations?view_op=medium_photo&user=BgiGGQQAAAAJ&citpid=4" alt="Mark D. Smucker" title="picture_mark_smucker" /></td>
        <td><b>Mark D. Smucker</b> <br> University of Waterloo <br> Waterloo, Ontario, Canada <br> <a href="https://uwaterloo.ca/management-science-engineering/profile/msmucker">Website</a> &nbsp; <a href="https://www.linkedin.com/in/mark-smucker-168144134/">LinkedIn</a> </td>
    </tr>
    <tr></tr>
    <tr>
        <td><img src="https://media.licdn.com/dms/image/C4E03AQErvMuxAKS8Qw/profile-displayphoto-shrink_400_400/0/1630422355651?e=1714003200&v=beta&t=Pqi9Pu2m8gbYyE1HCWe-9oaqgU6zdqyo56h1Oxslzqo" alt="Charles L. A. Clarke" title="picture_charles_clarke" /></td>
        <td><b>Charles L. A. Clarke</b> <br> University of Waterloo <br> Waterloo, Ontario, Canada <br> <a href="https://plg.uwaterloo.ca/~claclark/">Website</a> &nbsp; <a href="https://www.linkedin.com/in/charlie-clarke-7714a82/">LinkedIn</a> &nbsp; <a href="https://twitter.com/claclarke">Twitter</a></td>
    </tr>
</table>

## Resources
