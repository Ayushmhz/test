# Smart Study Assistant

Final project for the Building AI course

## Summary

An AI-powered learning companion that automatically transforms dense lecture notes and textbooks into structured study guides, flashcards, and practice quizzes. It helps students identify key concepts quickly and study more efficiently.


## Background

Students and lifelong learners spend hours manually summarizing reading materials and creating flashcards before they can even start studying. This administrative overhead leads to burnout and inefficient learning habits.

- High time investment spent manually creating study materials instead of active recall practice
- Difficulty in identifying core concepts and key technical terms within lengthy academic texts
- Lack of personalized quiz generation tailored specifically to a student's weak areas


## How is it used?

When a student prepares for an upcoming exam or review session, they upload their lecture notes, PDFs, or slides into the tool. The solution processes the text and presents interactive study aids.

The workflow integrates seamlessly into daily learning routines:
- **Input Setup:** The user uploads raw text or document files and selects desired output formats (e.g., summary, flashcards, or practice quiz).
- **Concept Extraction:** The system highlights main concepts, definitions, and relationships between terms.
- **Active Recall Practice:** The student tests their knowledge using automatically generated multiple-choice or short-answer questions.


## Data sources and AI methods

The solution utilizes public educational datasets, open textbooks, and user-provided lecture notes to extract knowledge structures and generate study materials.

| Resource Type | Description |
| ----------- | ----------- |
| Educational Corpora | Open-access academic articles and textbooks used for pre-training text summarization models |
| User Input Data | Raw lecture notes, slide transcripts, and reading assignments uploaded by the student |

```python
def generate_study_aids(lecture_notes, output_type='flashcards'):
   # Process raw text into clean tokens and sentences
   clean_text = preprocess_notes(lecture_notes)
   
   # Extract key concepts and definitions using keyword scoring
   key_concepts = extract_keywords_and_definitions(clean_text)
   
   # Generate requested study aid format
   if output_type == 'flashcards':
       return create_flashcard_pairs(key_concepts)
   elif output_type == 'quiz':
       return generate_practice_questions(key_concepts)
   
   return key_concepts

generate_study_aids("Neural networks consist of input, hidden, and output layers.", 'flashcards')
