# The Unofficial Guide

Manasa Manjunath, corpus: campus_life

> **This file is your submission.** Fill it in as you go — most sections get
> written during the milestone that produces them, not at the end.
>
> How the starter works, and every command you'll need, is in `RUNNING.md`.
> Leave that file alone.
>
> **Paste everything as text.** No screenshots, no video. A typed table gets
> full credit; a picture of the same table gets none.
>
> Delete these instruction blocks as you replace them. The `<!-- -->` comments
> are notes to you and don't show up when the page renders — you can leave them
> or remove them.

---

# Unit 1

## What This Does

<!-- Three or four sentences. Which corpus you picked, and the kinds of
     questions your system answers. Write it for someone who has never seen
     this repo.

     Milestone 5. -->

## Chunking Strategy

**Chunk size:**
**Overlap:**

<!-- What about YOUR documents made you pick these numbers? Short posts and
     long sectioned guides don't want the same chunking, and "800 seemed
     reasonable" earns nothing. Point at something you noticed when you read
     the documents in Milestone 1.

     If you changed your mind partway through, say so and say why. That's worth
     more than pretending you got it right first time.

     Milestone 3. -->

I updated my split_documents function to split based on paragraph break, but it gave separate chunks for headings, like
"PHYS 130 Mechanics — assessment" which is not useful and doesn't answer any question. So I decided to just reduce 
the chunk size and overlap

<!-- ======================================================================
Chunk 1  |  source: admin_add_drop_deadline.txt#0  |  produced by: chunker.py::split_documents
======================================================================
On the add/drop deadline You can add a course through the end of the second week. Dropping is a longer window — through the end of week six — but a drop after week two shows as a W on your transcript. Nothing anywhere on the registrar's site says this plainly, and students find out from each other.

======================================================================
Chunk 2  |  source: course_cs_340_exams.txt#2  |  produced by: chunker.py::split_documents
======================================================================
Start the term project in week three, not week eight; everyone learns this the hard way.

======================================================================
Chunk 3  |  source: course_phys_130_exams.txt#0  |  produced by: chunker.py::split_documents
======================================================================
PHYS 130 Mechanics — assessment

======================================================================
Chunk 4  |  source: housing_aldridge_hall.txt#0  |  produced by: chunker.py::split_documents
======================================================================
Aldridge Hall — what it's actually like

======================================================================
Chunk 5  |  source: housing_morrow_house_laundry.txt#0  |  produced by: chunker.py::split_documents
======================================================================
Laundry in Morrow House Machines take $1.50 wash, $1.25 dry, coin or card. There are eight washers and six dryers for the building, which is the wrong ratio and means the dryers back up on Sunday evenings. -->


## Sample Chunks

<!-- Five chunks, pasted as text. Label each one and name the file it came from
     AND the function that produced it — the grader checks your code against
     what you claim here.

     `python app.py chunks -n 5` prints all three for you. Copy them straight
     across.

     Milestone 3. -->

======================================================================
Chunk 1  |  source: admin_add_drop_deadline.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
On the add/drop deadline

You can add a course through the end of the second week. Dropping is a longer window — through the end of week six — but a drop after week two shows as a W on your transcript. Nothing anywhere on the registrar's site says this plainly, and students find out from each other.

======================================================================
Chunk 2  |  source: course_biol_160_exams.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
BIOL 160 Cell Biology — assessment

Four unit tests and a cumulative final. Not curved.

The unit tests come fast, roughly every three weeks; falling behind once is very hard to recover from.

======================================================================
Chunk 3  |  source: course_math_220.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
MATH 220 Linear Algebra

I lived here my sophomore year. Format is chalk-and-talk lecture, weekly problem sets marked for correctness. Assessment: two midterms and a cumulative final. Curved to a b- median.

Expect 6 to 8 hours a week, almost all of it on problem sets.

The one piece of advice: the problem sets are the course; the lectures make sense afterwards rather than during.

======================================================================
Chunk 4  |  source: dining_the_atrium_followup.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
Re: The Atrium

Adding to what people have said about The Atrium. The wait figure of no queue matches what I've seen. If you're trying to eat between classes, go before 11:45 and it's a different building entirely.

Also worth saying: picked clean by 1:15 and not restocked again until the next morning. Nobody tells you this at orientation.

======================================================================
Chunk 5  |  source: housing_innisfree_hall_laundry.txt#0  |  produced by: chunker.py::fallback_split
======================================================================
Laundry in Innisfree Hall

Machines take $1.75 wash, $1.75 dry, app-based. There are eight washers and six dryers for the building, which is the wrong ratio and means the dryers back up on Sunday evenings.

Best time to do laundry here is Tuesday or Wednesday morning. Sunday after 6pm you will wait.

## Sample Answer

<!-- One complete question and answer, pasted as text, with the source line
     visible. Milestone 4. -->

**Question:** (.venv) manasamanjunath@Manasas-MacBook-Air ai201-project1-unofficial-guide-starter-v2026 % python3 app.py ask "How long does unofficial transcripts take?" --show-prompt

**Answer:**

```
  (best distance 0.225, cutoff 0.48)

======================================================================
System instruction sent with the prompt
======================================================================
You answer questions using only the documents provided to you.

Rules:
- Use only the information in the documents below. Do not use anything you know from elsewhere.
- If the documents don't cover the question, say you don't have enough information. Do not guess.
- Name the document your answer came from, using the filename given in each excerpt.
- Be brief. Two or three sentences is usually enough.

======================================================================
The assembled prompt, exactly as sent
======================================================================
Documents:

[from admin_transcript_requests.txt]
On the transcript requests

Official transcripts cost $8 and take three business days electronically, or ten by post. Unofficial ones are free and instant from the student portal, and are accepted by most employers and by every graduate programme at the application stage.

[from admin_add_drop_deadline.txt]
On the add/drop deadline

You can add a course through the end of the second week. Dropping is a longer window — through the end of week six — but a drop after week two shows as a W on your transcript. Nothing anywhere on the registrar's site says this plainly, and students find out from each other.

[from admin_grade_appeals.txt]
On the grade appeals

A grade appeal starts with the instructor and has to be raised within fifteen days of the grade posting. Only after that does it go to the department. Skipping the instructor step gets the appeal returned, which wastes most of the fifteen days.

[from admin_withdrawal_deadline.txt]
On the withdrawal deadline

Withdrawal is a different thing from dropping and has a different date. Dropping ends at week six. Withdrawal runs to week ten, requires an adviser signature, and puts a W on the transcript that doesn't affect GPA. The two dates appear on different pages of the registrar's site and this catches people every year.

[from course_biol_160_workload.txt]
Workload for BIOL 160 Cell Biology

People keep asking so: 9 to 11 hours a week, the heaviest first-year course by reputation. That's real time, not optimistic time.

It's front-loaded — the first month is heavier than the rest, partly because you're learning the format.

---

Question: How long does unofficial transcripts take?

Answer using only the documents above, and name the file you used.
======================================================================

Unofficial transcripts are instant. 

Source: admin_transcript_requests.txt

Sources retrieved: admin_add_drop_deadline.txt, admin_grade_appeals.txt, admin_transcript_requests.txt, admin_withdrawal_deadline.txt, course_biol_160_workload.txt


```

**My relevance cutoff:**

<!-- The number you set in config.py, and how you got there.

     You ran five questions your corpus covers and the five in OUT_OF_SCOPE
     that it clearly doesn't, and wrote down the best distance for each. What
     did those two groups look like? Where was the gap? Put the actual numbers
     here — the table below wants all ten rows.

     Milestone 4. -->

threshold = 0.5 -> I set this number based on my observation of the gap in the best distance as printed below

| Question | In corpus? | Best distance |
| how many black-and-white pages can we print in a semester? | yes | 0.2528 |
| when should we expect extreme freezing temperatures? | yes | 0.4745 |
| when is the quiet hours in Morrow house? | yes | 0.3227 |
| when is the worst time to do laundry in Fenwick Court | yes | 0.2233 |
| How long does unofficial transcripts take? | yes | 0.2247 |
| What is the capital of Mongolia? | no | 0.8246 |
| How do I change the oil in a diesel engine? | no | 0.934 |
| Who won the 1994 World Cup? | no | 0.8095 |
| What is the recommended dosage of ibuprofen for a headache? | no | 0.8442 |
| How do I write a for loop in Rust? | no | 0.8326 |

## How I Used AI

<!-- Two specific moments. For each: what you asked for, what came back, and
     what you changed about it.

     "I asked Claude to write the chunking function from my notes. It ignored
     the overlap, so I added that myself" is the level of detail we're after.
     "I used AI to help me code" is not.

     Milestone 5. -->

**1.**
I asked Claude to help me with the chunking function. Since I picked the campus_life corpus I wasn't sure if
it even needed a different chunking strategy. Claude agreed to me. But I asked it if a document contains unrelated info
then its best to come up with a chunking strategy. It asked me how many posts are like that. If only 3-4 posts
contains multiple information in a single doc then its an edge case and wouldn't need more chunking, else it needs.
Since our corpus contains more than half of the documents with multiple information, I asked it to come up with a new chunking function. So we decided to chunk based on paragraph break. However this didn't seem to work since it created a new chunk for the title as well. When I noticed this in my chunk and gave it to claude it tried to fold the title to the first line. I didn't feel this is correct since the subsequent line is also related to the same title, and I was running out of time, so I decided to just reduce the chunk size and overlap and keep the chunking function as is.

**2.**
I asked claude to come up with a threshold. It matched with my expections.

<!-- ── Stretch features ─────────────────────────────────────────────────────
     Doing one? Say so here BEFORE you start. A feature this README never
     claims earns nothing.
     ───────────────────────────────────────────────────────────────────────── -->

---

# Unit 2

<!-- These sections get ADDED to what's already above. Don't delete or rewrite
     unit 1 — the point is that someone can see what you said before you knew
     how it went. -->

## Run Log — Before

<!-- Your five criteria, three runs each. `python run_eval.py --label before`
     runs the questions, puts the OUT_OF_SCOPE ones through the gate, and
     writes it all into results/ for you. Targets come from criteria.md; the
     verdict column is your call.

     Criterion 3 is measured in one deterministic pass rather than three, so
     the same number goes in all three run columns. That's correct, not lazy.

     Milestone 1. -->

| Criterion | Target | Run 1 | Run 2 | Run 3 | Verdict |
|---|---|---|---|---|---|
| 1. Retrieved chunk contains the answer | 4 of 5 |  |  |  |  |
| 2. Every answer names a source | 5 of 5 |  |  |  |  |
| 3. Gate stops out-of-corpus questions | 4 of 5 |  |  |  |  |
| 4. | | | | | |
| 5. | | | | | |

<!-- Underneath, paste the REAL output for each criterion from one of your
     runs — the actual text your system produced, not a description of it.
     Name the file and function that produced it. -->

## Verdicts

<!-- MET or MISSED for each of the five, against the target you wrote last
     unit — not a new one. Plus a sentence on how you decided. That sentence
     matters most where it was close.

     If your target said 4 of 5 and your runs came out 4, 3, 4, that's a MISS.
     The target has to hold, not show up occasionally.

     Milestone 2. -->

| # | Criterion | Verdict | How I decided |
|---|---|---|---|
| 1 |  |  |  |
| 2 |  |  |  |
| 3 |  |  |  |
| 4 |  |  |  |
| 5 |  |  |  |

## Diagnoses

<!-- For each miss: which stage caused it, and how. The stage alone isn't
     enough — you need the mechanism.

     Not a diagnosis: "Question 3 didn't work."
     A diagnosis:     "Question 3 asks about laundry costs. The answer is in
                       one sentence that got split across two chunks, so
                       neither chunk on its own contains it."

     The five stages: loading → chunking → embedding → retrieval → generation.

     Look for a pattern. If three misses all ask about numbers, that's one
     problem, not three.

     Missed nothing? Say so, then say honestly whether your targets were set
     low, and which one you'd tighten and to what.

     Milestone 3. -->

## The Improvement

**What I changed:**

**Why I picked it:**

<!-- Connect it to a specific diagnosis above in one sentence. If you can't,
     you picked a fix because it sounded impressive. -->

### Run Log — After

<!-- Same format, same five criteria, three runs each.
     `python run_eval.py --label after` -->

| Criterion | Target | Run 1 | Run 2 | Run 3 | Verdict |
|---|---|---|---|---|---|
| 1. Retrieved chunk contains the answer | 4 of 5 |  |  |  |  |
| 2. Every answer names a source | 5 of 5 |  |  |  |  |
| 3. Gate stops out-of-corpus questions | 4 of 5 |  |  |  |  |
| 4. | | | | | |
| 5. | | | | | |

**Did it help?**

<!-- Say plainly whether it did, and how you know. If it made things worse,
     say that — a change that backfired, honestly reported, earns full credit
     and is more interesting than one that worked. What matters is that you can
     tell.

     Milestone 4. -->

## What's Still Broken

<!-- For each criterion still missed after your fix: what you'd do about it,
     and why you stopped where you did.

     "I ran out of time" is fine if it's true. Pretending nothing is left is
     not.

     Milestone 5. -->

## What I'd Do Differently

<!-- Knowing what you know now — which of your five criteria would you write
     differently, and why?

     Milestone 5. -->
