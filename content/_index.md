---
weight: 1
title: 2024
type: docs
---

# TREC 2024 Lateral Reading Track Guidelines

**Please follow our Twitter account [@TREC_LR](https://twitter.com/TREC_LR) or Slack channel [#lateral-reading-2024](https://trectalk.slack.com/archives/C065QFMRNBY) for important announcements and discussions.**

## Overview

Welcome to the TREC 2024 Lateral Reading Track.
This is a venue for researchers interested in addressing the problems of misinformation and trust in search and online content.
The current web landscape requires the ability to make judgments about the trustworthiness of information, which is a difficult task for most people.
However, automated detection of misinformation is likely to remain limited to well-defined domains or be limited to simple fact-checking.

[Wineburg and McGrew (2019)](https://journals.sagepub.com/doi/abs/10.1177/016146811912101102) discovered that professional fact-checkers follow a process of **Lateral Reading** that involves asking questions about a document's sources and evidence and seeking answers to these questions via search engines in order to establish the document's trustworthiness.
In the first year of this track, our goal is to explore NLP and IR technologies to support the tested practice of Lateral Reading during people's trustworthiness evaluation of online news, given the civic importance of trustworthy news and a decline in trust in news over the years [(Brenan, 2022)](https://news.gallup.com/poll/403166/americans-trust-media-remains-near-record-low.aspx).
As such, it will not require a definition of what is true and what is misinformation, and thus the track can address trustworthiness beyond the relatively narrow focus of traditional fact-checking and claim verification.

While directed education on how to do Lateral Reading can be an effective means of helping people better evaluate the trustworthiness of information [(McGrew et al., 2019)](https://bpspsychub.onlinelibrary.wiley.com/doi/abs/10.1111/bjep.12279), this training cannot easily reach the millions of people who use the Internet and are finished with their schooling.
As such, an opportunity exists for systems to assist users with Lateral Reading by helping users understand what they should question about a document and helping them find other documents that can answer those questions.

In the first year, this track has two tasks with separate deadlines. 
For [Task 1](#task-1-question-generation), assuming there is a reader who is looking through an online news article, participants need to suggest questions that the reader should ask to determine its trustworthiness.
After the deadline for Task 1, we will release the questions NIST assessors come up with for [Task 2](#task-2-document-retrieval), where participants need to retrieve documents from the specified web collection to answer those questions.

<!--<img src="/lr_questions_example.png" alt="Example Questions for Lateral Reading" title="picture_lr_questions_example" style="border-radius: 0"/>-->

## Data

- **News Articles**: This [compressed file](/articles.zip) contains the plaintext version of our selected 50 news articles, each about a different event, published in 2021 and 2022 from various sources. 
- **Web Collection**: Task 2 will use the English subset `ClueWeb22-B-English` of the new [ClueWeb22](https://www.lemurproject.org/clueweb22.php/) Category B dataset as the document collection, which contains about 87 million popular web documents of roughly 200 GB data (size of plaintext).
This web collection was collected around February 2022. Please refer to their website for how to obtain the dataset.

Considering the size of `ClueWeb22-B-English`, we suggest you obtain the collection as soon as possible, ideally before the release of questions for Task 2.

## Tasks

As mentioned earlier, we have two tasks with separate submission due dates.

### Task 1: Question Generation

For each topic (news article), participants need to produce **10 questions** that the reader should ask to evaluate its trustworthiness, ranked by their importance to the evaluation from the most important to the least important. Those questions should meet the following requirements.
- Should be self-contained and explain the full context, i.e., one can understand this question without reference to the article.
- Should be at most 120 characters long.
- Should be reasonably expected to be answered by a single web page.
- Compound questions should be avoided, e.g. who is X and when did Y happen? In general, each question should focus on a single topic.

Participants should put all the questions for those 50 articles into a single file, using the format below, and submit it to the track organizers.
- It should be a tab-separated file.
- It should be encoded in UTF-8.
- Each line consists of the following tab-separated fields in this order: `topic_id`, `doc_id`, `run_tag`, `rank`, `question`.
    - `topic_id`: Found as the first line of the news article, which is also the name of the document.
    - `doc_id`: ClueWeb22 id, which is the second line of the news article.
    - `run_tag`: A unique tag for this run, which should be a combination of your team name (prefix) and your method.
    - `rank`: Rank of the question, starting from 1.
    - `question`: Question in plaintext, with no tabs or newlines.

Submissions can be either **manual** (involving human intervention to generate questions, e.g., hiring people to produce questions or manually selecting questions from a candidate list of questions produced by algorithms) or **automatic** (automatic systems to produce questions without the need of human input). After the submission due date of Task 1, we will make available the questions that NIST assessors raise during their evaluation of each news article.

Here is an example news article with 10 questions we came up with to support the reader's trustworthiness evaluation. On February 21, 2023, the New York Times published an opinion article by Bret Stephens entitled ["The Mask Mandates Did Nothing. Will Any Lessons Be Learned?"](https://www.nytimes.com/2023/02/21/opinion/do-mask-mandates-work.html?unlocked_article_code=gFPkTMW10NLmmWAaYVT8kUk5IJGdtqOT4oPTIljn-eqha-dQGMt5LbDNkcSGc-lPWwq88xHQztwlyXkwSvjA42AWwawLMaAd0GruPyysGxIHa4izksvdo7Rzs08-EuiXyFTG01aeEWnRqUzneqq92uwtQH8FPvptgSBG2nc2u5i7JZ-Q5yMFli4VgmS1-2XMEPxw4ZX_-FXhpdOse85-TnFMOHW1Oc1r0347aFhJ73iOcuIs6nBJu8GERP8f9dqxnFtJ_km19GyZsJCtPv7Q9I3RNo4ozPwIhlV0nqJfDGiOwP3GTfFyFh_OuqglmGDh3UAmSRtWsP0IhiGu&smid=url-share). This [Google Document](https://docs.google.com/document/d/1qj2QZDz0ZTWukULId1-hYg2Cva2rmS13fk56WE192Jw/edit?usp=sharing) contains the plaintext version of this article. Stephens makes an argument that mask mandates during the COVID pandemic did not work. Given the importance of this issue, the reader would be advised to examine the trustworthiness of the information.
As suggested by Lateral Reading, we want to ask about sources, evidence, and what others say about the issue. This [example file](/lateral-eg.txt) shows the 10 questions we came up with to evaluate the trustworthiness of this article, based on its plaintext version in the Google Document. In working to answer these questions, the reader would likely learn that Stephens is a conservative, that Tom Jefferson had previously published articles using other studies as evidence against masks, which received criticism from other scientists, that Maryanne Demasi is a journalist who has faced criticism for reports that go against scientific consensus, e.g. Wi-Fi is dangerous, and that the Cochrane study was misinterpreted as it was inconclusive about the question of if interventions to encourage mask wearing worked or not. This example file is what we expect participants to return for all the 50 articles.

### Task 2: Document Retrieval

After the due date of Task 1, we will release the questions produced by NIST assessors, 10 for each article.
Participants need to retrieve 10 documents from the web collection `ClueWeb22-B-English` that help answer those questions, ranked by their usefulness.
This task is similar to a traditional ad-hoc retrieval task.
As we will provide questions, to participate in Task 2 does not require your participation in Task 1.
You can choose to participate in either one or both tracks.

Similar to Task 1, runs may be either automatic or manual.
Submissions should follow the standard TREC run format below.
- It should be a space-separated file.
- It should be encoded in UTF-8.
- Each line consists of the following tab-separated fields in this order: `query_id`, `Q0`, `doc_id`, `rank`, `score`, `run_tag`.
    - `query_id`: Query id, which is a combination of the topic id and the question rank, e.g., 101 is the first question for the first news article.
    - `Q0`: Unused column, whose value should be `Q0`.
    - `doc_id`: ClueWeb22 id of the retrieved document.
    - `rank`: Rank of the document, starting from 1.
    - `score`: Score (integer or floating point) of the document, in non-increasing order. [trec_eval](https://trec.nist.gov/trec_eval/) sorts documents by the scores instead of the ranks.
    - `run_tag`: A unique tag for this run, which should be a combination of your team name (prefix) and your method.

## Schedule

- **Task 1 Article Released**: April 23
- **Task 1 Question Generation <u>Submission Due</u>**: June 30
- **Task 2 Question Release**: Early July
- **Task 2 Document Ranking <u>Submission Due</u>**: August
- **Result Release**: Late September
- **Notebook <u>Paper Due</u>**: Late October
- **TREC 2024 Conference**: November 18-22 at NIST in Gaithersburg, MD, USA

## Evaluation

NIST assessors will judge the usefulness of generated questions from Task 1 and the usefulness of retrieved documents to answer the corresponding question in the context of the news article from Task 2.
Evaluation details are to be determined.

## Q&A

1. How do we register to participate in this track? \
Please follow the TREC registration guidelines from their [Call for Participation](https://trec.nist.gov/pubs/call2024.html).
2. Why can't we join the Slack channel? \
[#lateral-reading-2024](https://trectalk.slack.com/archives/C065QFMRNBY) is in the TREC workspace. Please join the workspace first by following the instructions in the TREC 2024 welcome email after registration.

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
- <a href="https://cor.inquirygroup.org/curriculum/collections/teaching-lateral-reading">Civic Online Reasoning - Teaching Lateral Reading</a>
