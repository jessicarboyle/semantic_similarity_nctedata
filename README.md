# Semantic Similarity of Teachers’ Classroom Discourse Linked to Quality Ratings from Classroom Observations 
**Overview:**

This analysis assessed the cohesiveness of teacher discourse during classroom instruction to explore its relationship with a widely used observational measure of instructional quality. The study used classroom transcripts, specifically focusing on teacher dialogue, drawn from a nationally representative da-taset of observations in elementary math classrooms [7]. Each transcript was paired with corresponding quality ratings from Classroom Atmosphere Scoring System (CLASS) observations completed by expert raters. The CLASS is an observational tool used to assess teacher and student social and instruction-al interactions, as well as the intentionality and productivity of the classroom context [8]. The CLASS scores selected for this study included Instructional Dialogue, Instructional Sup-port, and an overall quality rating. 


To assess the cohesiveness of teachers’ discourse, spaCy was used to calculate the semantic similarity between adjacent teacher utterances. This was completed for all words in each teacher utterance and exclusively for the content words in each utterance. This analysis examines the semantic similarity be-tween teachers' adjacent utterances and its relation to the qual-ity ratings for instructional dialogue, instructional support, and the overall CLASS score.


**Data:**

The open-source National Center for Teacher Effectiveness (NCTE) transcript dataset includes anonymized transcripts from teachers’ classroom observations from the NCTE Main Study [20]. The observations occurred between 2010-2013 in 4th and 5th-grade elementary math classrooms across four dis-tricts, predominately serving historically marginalized stu-dents. The transcripts are linked with a variety of outcome variables including classroom observation scores, demograph-ic information, survey responses, and student scores. The en-tire NCTE dataset can be found at: https://github.com/ddemszky/classroom-transcript-analysis. This analysis focused on the classroom transcripts and the linked Classroom Atmosphere Scoring System (CLASS) data. 

**Classroom Transcripts

This analysis includes 1325 observation transcripts from 301 teachers, each with an average of 4 transcripts. Classroom les-sons were captured using three cameras, a lapel microphone for teacher talk, and a bidirectional microphone for student talk. The recordings were transcribed by professional transcribers working under contract for a commercial transcription compa-ny. 
The transcripts were organized by speaker turns (teacher, stu-dents, multiple students) where each row of the transcript data frame represents a speaker turn or utterance that may contain one or more speech acts or "sentences". In this analysis, stu-dent talk was removed and only teacher turns were analyzed. On average, the transcripts contain 5,733 words, with 87.7% of which are spoken by the teachers, and with 172 teacher ut-terances per transcript.
The transcripts are fully anonymized: student and teacher names are replaced with terms like “Student J”, “Teacher” or “Mrs. H”. Transcribers used square brackets to indicate when speech was [Inaudible], if they were unsure of a particular word due to audio quality, or to include meta-data such as [laughter], [students putting away materials]. All bracketed information was removed from the transcripts for this analy-sis. 


**Classroom Assessment Scoring System (CLASS) Scores

The CLASS includes 3 domains and 11 sub-dimensions meas-uring teacher-student interactions. This analysis includes the overall CLASS score, the Instructional Support domain, and the Instructional Dialogue dimension. Observers score each dimension using a 7-point scale.
The overall CLASS score represents the teachers' average abil-ity across the 3 domains and 11 dimensions. The Emotional Support domain includes the Positive Climate, Teacher Sensi-tivity, and Regard for Student Perspectives dimensions; the Classroom Organization domain includes the Behavior Man-agement, Productivity, and Negative Climate dimensions; and the Instructional Support domain includes the Instructional Learning Format, Content Understanding, Analysis and In-quiry, Quality Feedback, and Instructional Dialogue dimen-sions. 
The Instructional Support domain measures the teachers' in-structional support ability to enhance learning through con-sistent, process-oriented feedback, focus on higher-order thinking skills, and presentation of new content within a broader, meaningful context. The instructional support domain score is calculated by taking an average of its' 5 dimensions' scores.
The Instructional Dialogue dimension is defined as the pur-poseful use of cumulative content-focused discussion among teachers and students. It measures whether teachers actively support students in connecting ideas and fostering a deeper understanding of the content. Lower scores (1,2) are assigned when there are minimal or no discussions in the classroom, and when the teacher seldom acknowledges, repeats, or ex-tends on comments. Mid-range scores (3,4,5) are given when discussions occur, but they are brief or shift rapidly between topics without subsequent questions or comments. Higher scores (6,7) indicate the presence of frequent, content-driven discussions between teachers and students, fostering cumula-tive exchanges where teachers actively promote elaborate dia-logue through open-ended questions and repetitions.


**Code Included:**

**.ipyn file

This codes includes data cleaning and the semantic similarity analysis. For the analysis that included all the words, punctuation was removed from the original NCTE transcripts. This step was critical due to the arbitrary nature of punctuation in the tran-scription of spoken language, where people often express themselves without strictly adhering to conventional written sentence structures, especially in a context such as a class-room. Eliminating punctuation ensured the analysis focused on the teachers’ words and the semantic similarity scores were not impacted by punctuation. For the analysis that included only content words, The Natural Language Toolkit (NLTK) was used to remove stop words, a predetermined set of commonly used words (e.g., a, the, is) that carry minimal useful information. By filtering out the stop words, the analysis isolated essential content words, provid-ing a focused examination of words carrying the primary mes-sage in the teachers’ utterances. Both analyses used spaCy’s large English model to calculate the semantic similarity scores.

**.rmd file

This code includes the statistical analysis examining the relationship between semantic similarity scores and the CLASS measures. It includes descriptive analsysis and correlations.




