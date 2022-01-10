# Aditya's Research Log :notebook: (Winter 2022)
---

## Week 1 (1/3-1/9)

## January 9th, Sunday (1 hour)
**Group Meeting**
  * Created schedule (daily stand-ups, weekly meeting, Thursday Review, planning meeting)
  * Goals: [Group Log To-Do Week 2](https://docs.google.com/document/d/1LcdXGe6vLvuyqFmYcSWpXD0GPnwAC19ObRCHeW-ITls/edit#heading=h.yb9nyo94cuhq)

- [ ] Watched [Vector based methods for Similarity Search  (TF-IDF, BM25, SBERT)](https://www.youtube.com/watch?v=ziiF1eFM3_4)

**Takeaways from Video**
  * Sparse Methods: TF-IDF & BM25 | Dense Representation: SBERT
  * **TF-IDF**:
    * Ex: `“There is an art to getting your way and throwing [bananas] on to the street is not it”`
    * `TF = f(q,D)/f(t,D)`
    * Term Frequency is the frequency of the query in the document say “bananas” divided by the frequency of terms in the document 
    * `IDF = log(N/N(q))`
    * IDF (Inverse Document Frequency) 
    * Say a common word “the” appears in all documents, therefore, # documents/# documents containing the query = 1. log(1) = 0, therefore this word doesn’t matter at all (not a relevant word).
    * `Final Score = TF * IDF`
  * **BM-25: Optimized version of TF-IDF**
    * Problem with TF-IDF, if we have a word appearing x number of times in a document. If another document has 2x number of words, then the TF-IDF score doubles. This would mean that the 2nd document is 2 times more relevant, but is that always true?
    * BM25 helps normalize this
  * ```
    BM25 = [ f(q,D) * (k+1) / f(t,D) + k* (1 - b + b*D/d_Avg) ] * 
    log(N - N(q)+ 0.5/N(q) + 0.5 + 1)
    
    K = ~1.25, b = ~0.75 (constants), D = document length, d_Avg = all doc len/N
  * SBERT: dense representation of language
    * Sparse vs Dense: 
      * [0, 0, 0.2] sparse
      [0.1, 0.23, 0.3, …] dense 
    * BERT encoding layers
    * Queries and documents fed inside BERT
    * Cosine Similarity - cosine(Q[.. ..]  D[.. ..])
      * Greater angle theta = less similar, Smaller angle theta = more similar


## January 8th, Saturday (1 hour)
* Read Chapter 4: Naive Bayes and Sentiment Classification of Jurafsky Textbook
* Watched YouTube Review video on [N-gram Language Models](https://www.youtube.com/watch?v=P3d7D78Cj1E).

**Notes from [Leveraging Passage Retrieval with Generative Models for Open Domain Question Answering](https://arxiv.org/pdf/2007.01282.pdf)** (Facebook AI Research)
* Generative Models are difficult without use of external knowledge
  * Requires models with billions of parameters
  * Expensive to train and query
* Performance of the models significantly improves with increasing number of retrieved passages

## January 7th, Friday (3.5 hours) 
**ERSP Meeting with Chinmay** :calendar:
  * ERSP Presentations will start from next week (push by one week due to scheduling)
  * Keep logs update-to-date for CS 196 (individual + group logs)
  * Each week create 1-2 slides for what you have done that particular week

Annotated ~20 more question-answer pairs in spreadsheet
Created pie chart to represent the data

**NLP Lab Reading Group Meeting** :calendar: :book:
Professor William Wang presented Intro for Winter 2022 Quarter
* AI: The most competitive area in Computer Science
  * 70% of all CS PhDs work in AI.
  * Used in AI, Systems/Architecture, Algorithms, Robotics, Mathematics Research
  * Stats: number of AI-related publications on arXiv grew more than 600% (5,478 in 2015 to 34,736 in 2020)
  * **Quick Turnarounds and agile development cycles** measured in short-term and long-term goals, all research projects must be rock solid: open-source and reproducible.
* Disseminating Knowledge
  * PhD students should share knowledge of their work: give talks at groups, at workshop, at event, or even social media
  * Thousands of papers being accepted to NeurIPS and ACL NLP Conferences, new requirement that people should recognize your hard work
  * If you don't share your work on social media, no one will read your paper
* Upcoming Conferences
  * IJCAI, ICML Jan 2022, NAACL 2022 (Jan 15), EECV 2022 (Mar 7th), NeurIPS/EMNLP Conferences
* Summer Internships: Research Scientist Positions
  * Is it research based? Can it lead to a publication?
  * Can it help you get a letter writer?
  * How does it benefit your thesis?
  * Don't work on research internship during school year, part-time PhD student not allowed (hurt your UCSB research)



**NLP ERSP Research Meeting** :star:
* Takeaways
  * Deep Learning does computer pattern matching, we need to check our 100 QA pair with Fusion-incoder model and Deep Passage Retrieval model
    * Hands-on experience with state-of-the-art models in ML
    * Need metric to show this dataset is challenging
  * Scale up quickly from 100 to larger amount
    * Recent QA dataset size minimum 10K-20K (target ~20K)
    * May need to run more than 20K since some QA pairs would be dropped
    * Make a concrete budget plan
  * Go through the pipeline phases
  * HybridQA (Paper by Wenhu Chen, past student in NLP lab)
    * Contact Wenhu Chen
    * Ask how to deal with validation
    * Idea: Auto-reject bad questions by putting a dummy QA pair
  * Read Google TidyQA (200K QA pairs)
* Timeline
  * March 15th ACL paper deadline
  * Dataset collection 1 month max
    * Most important part: `quality of the dataset`
  * ML Reading Comprehension + Passage Retrieval 1 month
  * About a week to write the paper

### January 6th, Thursday (3 hours)
* Meeting with Group
  * Discussion about Stage 1 (simple) Pipeline
    * 100 QA Pairs: 50 Free-form Questions, 30 Fact-based, 20 Stack Exchange Questions
    * MTurk Task launched over break and ready for annotation
  * **Brainstorm QA Pair Validation Pipeline Stage and Question Drop Mechanism**
    * Does Question make sense?
    * Does Answer make sense?
    * Is there evidence in Wikipedia to support?
    * If not, then we need to decide if we are going to 
      1. Drop the Question
      2. Rephrase the Question/Answer Pair
    * Issues: we need to keep track on branching steps

Accomplishments:
- [x] Annotated 20 Stack-exchange Questions
- [x] Prepared talking points for Friday's ERSP Meeting (below)
- [x] Brainstorm QA Pair Validation Techniques

* Friday Meeting Topics
  - [ ] Scheduling for future week's meeting
  - [ ] NLP Server Access and Setup
  - [ ] DPR and FiD RAM Usage (GPU's needed)
  - [ ] Share Pipeline Stage 1 Results
  - [ ] Resulting Annotations Stage 1
  - [ ] Future Stages to Launch 

### January 5th, Wednesday (1 hour)
- [ ] Take Notes on [Dense Passage Retrieval for Open-Domain Question Answering](https://arxiv.org/pdf/2004.04906.pdf)
- [ ] Read [Leveraging Passage Retrieval with Generative Models
for Open Domain Question Answering](https://arxiv.org/pdf/2007.01282.pdf)

**Notes from [Dense Passage Retrieval (DRP)]((https://arxiv.org/pdf/2004.04906.pdf))**
* Background
  * Open-Domain Question Answering (QA) is a task that answers factoid questions using large collection of datasets
  * Reading Comprehension Models two-stage framework: (1) context retriever selects small subset of passages containing answers (2) machine reader examines and identify correct answer
  * TF-IDF & BM25: Matches keywords efficiently with inverted index, represents question and context in high-dimensional sparse vectors
  * Retrieval done with Maximum Inner Product Search (MIPS) Algorithm in-memory data structure
* Proposal: Train better dense embedding model using pairs of questions and passages
  * Dense Passage Retrieval: embedding optimized for maximizing inner products of the question and relevant passage vectors
  * Dense encodings are more powerful, learnable functions
  * Leverages BERT and dual encoder architecture
  * Outperforms BM25 by large margin (65.2%)
  * Results in substantial improvement on end-to-end QA accuracy when compared against Natural Questions setting


### January 4th, Tuesday (1 hour)
* ERSP Team Presentation: 4:00 - 4:15pm
* ERSP check-in with Professor Mirza: 4:15 - 4:45pm

- [ ] Read [Dense Passage Retrieval for Open-Domain Question Answering](https://arxiv.org/pdf/2004.04906.pdf)

### January 3rd, Monday (1 hour)
* Team Communication over Slack
* CS 190I: Introduction to Natural Language Processing :robot:
  * Course taught by Professor William Wang
* **ERSP Group Presentation 1/13** on Zoom
  * 15 minutes for Proposal and Q&A 
* Meetings Schedule :calendar: :
  * **NLP Research Meeting:** Friday's 3:00-4:00 pm
  * **Reading Group Meeting:** Friday's 12:00pm
  * **ERSP Meeting:** Friday's 6:30 - 7:00pm