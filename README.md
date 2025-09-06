Apgar Smart Academy Demo: Course Recommendation and Facial Recognition App  

## Project Overview  

This project was developed during the **Smart Academy Challenge** organized by Apgar. In just six hours, our team designed a prototype application for the **Apgar Smart Academy**, a demo platform intended to recommend courses to users based on their interests while ensuring secure login through facial recognition.  

The prototype integrates:  
- **Streamlit interface** for the user experience  
- **Facial recognition** for authentication  
- **PDF parsing** to extract course details  
- **NLP (Natural Language Processing)** for text matching and recommendations  
- **Pickle (.pkl files)** to manage user data and face encodings  

<div align="right" style="font-size:16px; color:black; font-family:Segoe UI, sans-serif;">  
Developed by Sabine Allam & Team  
As part of the *Smart Academy Challenge* at Apgar  
</div>  

---

## Table of Contents  
- [Project Overview](#project-overview)  
- [Part 1: User Authentication](#part-1-user-authentication)  
- [Part 2: Course Catalog Parsing](#part-2-course-catalog-parsing)  
- [Part 3: Course Recommendation Engine](#part-3-course-recommendation-engine)  
- [Part 4: Application Interface](#part-4-application-interface)  
- [Requirements](#requirements)  
- [How to Run](#how-to-run)  

---

## Part 1: User Authentication  

The app implements facial recognition for secure user login.  

### Key Features:  
- **Face detection & encoding:** Uses OpenCV and the `face_recognition` library.  
- **Dataset management:** User data (IDs, names, images, encodings) is stored in pickle files.  
- **Authentication:** Successful matches automatically redirect the user to the quiz/recommendation module.  

---

## Part 2: Course Catalog Parsing  

Course details are stored in a PDF document and parsed automatically.  

### Key Features:  
- **Parsing:** Extracts course names, descriptions, and schedules using `PyPDF2`.  
- **Cleaning:** Handles irregular formatting to produce structured text.  
- **Output:** Builds a structured table of courses for use in recommendations.  

---

## Part 3: Course Recommendation Engine  

Natural language processing (NLP) is used to align user interests with course descriptions.  

### Key Features:  
- **Preprocessing:** Spelling correction (`TextBlob`), synonym expansion (`NLTK WordNet`), normalization.  
- **Vectorization:** Converts text to vectors with spaCy (`en_core_web_md`).  
- **Similarity Matching:** Computes cosine similarity between user input and course descriptions.  
- **Filtering:** Matches courses by both availability and similarity score thresholds.  

---

## Part 4: Application Interface  

The interface is designed with Streamlit to provide a user-friendly experience.  

### Key Features:  
- **Landing page:** Intro, course catalog display, and navigation.  
- **User profile management:** Login/Signup via facial recognition or manual input.  
- **Interactive quiz:** Guides users through entering availability and interests.  
- **Recommendations:** Displays ranked course suggestions with details and similarity scores.  

---

## Requirements  

- **Python 3.10+**  
- **Libraries:**  
  - `streamlit` – interface design  
  - `opencv-python` – image capture & preprocessing  
  - `face_recognition` – face detection and encoding  
  - `spacy` – NLP and vectorization (requires `en_core_web_md` model)  
  - `nltk` – synonym expansion via WordNet  
  - `textblob` – spelling correction  
  - `pandas`, `numpy` – data handling  
  - `PyPDF2` – PDF parsing  
  - `pickle` – for managing user data and face encodings  

---

## How to Run  

Check Word Document "FinalProject_HowToRun"

---

## Notes and Future Enhancements  

**Note:** This project was developed in only six hours as part of a technology challenge. It is a prototype and contains several limitations, and so, there are many opportunities for further development.  

### Potential Improvements:  
- **Access control:** Require users to log in before accessing main pages, with gated navigation based on authentication status.  
- **Smarter recommendations:** Integrate advanced language models (e.g., OpenAI APIs) to better match user interests with course descriptions.  
- **Role-based authentication:** Create separate login flows for students and instructors, with different permissions and features.  
- **Scalability:** Replace pickle files with a more robust database solution and explore deployment on cloud platforms.  
- **Personalized memory:** Extend the database to also store user interests, so the system can remember preferences across sessions, with options to clear or reset history.
- **Course management:** Add multiple ways to include courses (e.g., parsing PDFs, uploading CSVs, or manual entry via the interface).
- **Multi-language support:** Add a language switcher to the interface to make the app accessible to a wider audience.  
- **User experience:** Enhance the design with more intuitive layouts, progress indicators, and responsive styling.  

These steps would strengthen the prototype into a more reliable and scalable application, while keeping its core goal: connecting users with the courses most relevant to them.  
