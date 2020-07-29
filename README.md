## Full Stack Trivia API Project - Udacity

This project was completed as part of the course requirements of Udacity's Full Stack Nanodegree certification. A webpage created to manage the Trivia  app to play a game that contain trivai questions to test users knowledgeability. In addtion, users can search about questions based on text,
add questions with categories and difficulty levels, and see a list of questions based on categories.


- The task for the project was to create an API and test suite for implementing the following functionality:

1) Display questions
both all questions and by category. Questions should show the question, category and difficulty rating by default and can show/hide the answer.

2) Delete questions.

3) Add questions and require that they include question and answer text.

4) Search for questions based on a text.

5) Play the quiz game, randomizing either all questions or within a specific category. 

### Objective:
Completing this trivia app project will give me the ability to structure plan, implement, and test an API skills essential for enabling my future applications to communicate with others.  

## About the Stack:

### Backend

The `./backend` directory contains a partially completed Flask and SQLAlchemy server. I work primarily in app.py to define my endpoints and can reference models.py for DB and SQLAlchemy setup. 

### Frontend

The `./frontend` directory contains a complete React frontend to consume the data from the Flask server. I need to update the endpoints after define them in the backend. 

## Getting Started

# Installing Dependencies

Python 3.7:
Developers using this project should already have Python3, pip, node, and npm installed.


Virtual Enviornment:
It's recommended to worke within a virtual environment whenever using Python for projects. This keeps the dependencies for each project separate and organaized.


Frontend Dependencies:
This project uses NPM to manage software dependencies. NPM Relies on the package.json file. It's located in the frontend directory of this repository. After cloning, I open my terminal and run:

npm install

Backend Dependencies:
PIP Dependencies:
Once I have your virtual environment setup and running. I install dependencies by naviging to the /backend directory and running:

pip install -r requirements.txt

This will install all of the required packages that selected within the requirements.txt file.

Key Dependencies:

A- Flask is a lightweight backend microservices framework. Flask is required to handle requests and responses.

B- SQLAlchemy is the Python SQL toolkit and ORM we'll use handle the lightweight sqlite database. You'll primarily work in app.py and can reference models.py.

C- Flask-CORS is the extension we'll use to handle cross origin requests from our frontend server.

### Database Setup
With Postgres running, restore a database using the trivia.psql file provided. From the backend folder in terminal run:

psql trivia < trivia.psql

### Running the Frontend in Dev Mode
The frontend app was built using create-react-app. In order to run the app in development mode I use npm start. 

after that I open http://localhost:3000 to view it in the browser. The page will reload if I make edits on it.

npm start

### Running the Server
When using the backend directory I have first to ensure that I working on my created virtual enviroment.

- To run the server, execute:

export FLASK_APP=flaskr
export FLASK_ENV=development
flask run

- Setting the FLASK_ENV variable to development will detect file changes and restart the server automatically.

- Setting the FLASK_APP variable to flaskr directs flask to use the flaskr directory and the __init__.py file to find the application.


### API documentation
- API Reference:

Getting Started:
- URL: Currently this application is only hosted locally. The backend is hosted at http://127.0.0.1:5000/

- Endpoints:
1- POST /questions with search term included in request:
curl http://127.0.0.1:5000/questions -X POST -H "Content-Type: application/json" -d '{"searchTerm": "Van Gogh"}'
{
  "questions": [
    {
      "answer": "One", 
      "category": 2, 
      "difficulty": 4, 
      "id": 18, 
      "question": "How many paintings did Van Gogh sell in his lifetime?"
    }
  ], 
  "success": true, 
  "total_questions": 20
}

2-POST /questions with no search term included in request:
curl http://127.0.0.1:5000/questions -X POST -H "Content-Type: application/json" -d '{ "question": "How many paintings did Van Gogh sell in his lifetime?", "answer": "One", "difficulty": 4, "category": "2" }'
{
  "created": 78, 
  "question_created": "How many paintings did Van Gogh sell in his lifetime?", 
  "questions": [
    {
      "answer": "Tom Cruise", 
      "category": 5, 
      "difficulty": 4, 
      "id": 4, 
      "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
    }, 
    {
      "answer": "Maya Angelou", 
      "category": 4, 
      "difficulty": 2, 
      "id": 5, 
      "question": "Whose autobiography is entitled 'I Know Why the Caged Bird Sings'?"
    }, 
    {
      "answer": "Muhammad Ali", 
      "category": 4, 
      "difficulty": 1, 
      "id": 9, 
      "question": "What boxer's original name is Cassius Clay?"
    }, 
    {
      "answer": "Brazil", 
      "category": 6, 
      "difficulty": 3, 
      "id": 10, 
      "question": "Which is the only team to play in every soccer World Cup tournament?"
    }, 
    {
      "answer": "Uruguay", 
      "category": 6, 
      "difficulty": 4, 
      "id": 11, 
      "question": "Which country won the first ever soccer World Cup in 1930?"
    }, 
    {
      "answer": "George Washington Carver", 
      "category": 4, 
      "difficulty": 2, 
      "id": 12, 
      "question": "Who invented Peanut Butter?"
    }, 
    {
      "answer": "The Palace of Versailles", 
      "category": 3, 
      "difficulty": 3, 
      "id": 14, 
      "question": "In which royal palace would you find the Hall of Mirrors?"
    }, 
    {
      "answer": "Agra", 
      "category": 3, 
      "difficulty": 2, 
      "id": 15, 
      "question": "The Taj Mahal is located in which Indian city?"
    }, 
    {
      "answer": "Escher", 
      "category": 2, 
      "difficulty": 1, 
      "id": 16, 
      "question": "Which Dutch graphic artist\u2013initials M C was a creator of optical illusions?"
    }, 
    {
      "answer": "One", 
      "category": 2, 
      "difficulty": 4, 
      "id": 18, 
      "question": "How many paintings did Van Gogh sell in his lifetime?"
    }
  ], 
  "success": true, 
  "total_questions": 23
}


3- DELETE /questions/<int:id>
 curl http://127.0.0.1:5000/questions/17 -X DELETE
{
  "deleted": 17, 
  "success": true
}


4- GET /questions:
curl http://127.0.0.1:5000/questions
{
  "categories": {
    "1": "Science", 
    "2": "Art", 
    "3": "Geography", 
    "4": "History", 
    "5": "Entertainment", 
    "6": "Sports"
  }, 
  "questions": [
    {
      "answer": "Maya Angelou", 
      "category": 4, 
      "difficulty": 2, 
      "id": 5, 
      "question": "Whose autobiography is entitled 'I Know Why the Caged Bird Sings'?"
    }, 
    {
      "answer": "Muhammad Ali", 
      "category": 4, 
      "difficulty": 1, 
      "id": 9, 
      "question": "What boxer's original name is Cassius Clay?"
    }, 
    {
      "answer": "Tom Cruise", 
      "category": 5, 
      "difficulty": 4, 
      "id": 4, 
      "question": "What actor did author Anne Rice first denounce, then praise in the role of her beloved Lestat?"
    }, 
    {
      "answer": "Brazil", 
      "category": 6, 
      "difficulty": 3, 
      "id": 10, 
      "question": "Which is the only team to play in every soccer World Cup tournament?"
    }, 
    {
      "answer": "Uruguay", 
      "category": 6, 
      "difficulty": 4, 
      "id": 11, 
      "question": "Which country won the first ever soccer World Cup in 1930?"
    }, 
    {
      "answer": "George Washington Carver", 
      "category": 4, 
      "difficulty": 2, 
      "id": 12, 
      "question": "Who invented Peanut Butter?"
    }, 
    {
      "answer": "The Palace of Versailles", 
      "category": 3, 
      "difficulty": 3, 
      "id": 14, 
      "question": "In which royal palace would you find the Hall of Mirrors?"
    }, 
    {
      "answer": "Agra", 
      "category": 3, 
      "difficulty": 2, 
      "id": 15, 
      "question": "The Taj Mahal is located in which Indian city?"
    }, 
    {
      "answer": "Escher", 
      "category": 2, 
      "difficulty": 1, 
      "id": 16, 
      "question": "Which Dutch graphic artist\u2013initials M C was a creator of optical illusions?"
    }, 
    {
      "answer": "Mona Lisa", 
      "category": 2, 
      "difficulty": 3, 
      "id": 17, 
      "question": "La Giaconda is better known as what?"
    }
  ], 
  "success": true, 
  "total_questions": 21
}


5- GET /categories/<int:id>/questions:
 curl http://127.0.0.1:5000/categories/1/questions
{
  "current_category": "Science", 
  "questions": [
    {
      "answer": "The Liver", 
      "category": 1, 
      "difficulty": 4, 
      "id": 20, 
      "question": "What is the heaviest organ in the human body?"
    }, 
    {
      "answer": "Alexander Fleming", 
      "category": 1, 
      "difficulty": 3, 
      "id": 21, 
      "question": "Who discovered penicillin?"
    }, 
    {
      "answer": "Blood", 
      "category": 1, 
      "difficulty": 4, 
      "id": 22, 
      "question": "Hematology is a branch of medicine involving the study of what?"
    }
  ], 
  "success": true, 
  "total_questions": 21
}


6- POST /quizzes:
curl http://127.0.0.1:5000/quizzes -X POST -H "Content-Type: application/json" -d '{"previous_questions": [20, 21], "quiz_category": {"type": "Art", "id": "3"}}'
{
  "question": {
    "answer": "The Palace of Versailles", 
    "category": 3, 
    "difficulty": 3, 
    "id": 14, 
    "question": "In which royal palace would you find the Hall of Mirrors?"
  }, 
  "success": true
}


7- GET /categories:
 curl http://127.0.0.1:5000/categories
{
  "categories": {
    "1": "Science", 
    "2": "Art", 
    "3": "Geography", 
    "4": "History", 
    "5": "Entertainment", 
    "6": "Sports"
  }, 
  "success": true
}


- Errors Handling are returned as JSON in the following format:
1- curl http://127.0.0.1:5000/categories/200/questions
{
  "error": 400, 
  "message": "Bad Request", 
  "success": false
}

2- curl http://127.0.0.1:5000/categories/200
{
  "error": 404, 
  "message": "Resource Not Found", 
  "success": false
}

3- curl -X DELETE http://127.0.0.1:5000/questions/20000
{
  "error": 422, 
  "message": "Unprocessable", 
  "success": false
}


### Testing
To run the tests, you have to run:

createdb trivia_test
psql trivia_test < trivia.psql
python test_flaskr.py

### Authors:
Your Student, Tadhi Ibrahim.

### At The End:
All other project files, including the models and frontend, were created by Udacity.
