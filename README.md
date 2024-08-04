<a name="readme-top"></a>
<!-- TABLE OF CONTENTS -->
<details>
  <summary>Table of Contents</summary>
  <ol>
    <li>
      <a href="#about-the-project">About The Project</a>
      <ul>
        <li><a href="#built-with">Built With</a></li>
      </ul>
    </li>
    <li>
      <a href="#getting-started">Getting Started</a>
      <ul>
        <li><a href="#prerequisites">Prerequisites</a></li>
        <li><a href="#installation">Installation</a></li>
        <li><a href="#project-explorer">Project Explorer</a></li>
      </ul>
    </li>
    <li><a href="#key-features">Key Features</li>
    <li><a href="#usage">Usage</a></li>
    <li><a href="#references">References</li>
    <li><a href="#contact">Contact</a></li>
  </ol>
</details>

<p align="center">
    <img src="/images/logo.png" width="96" height="96">
    &nbsp; <strong>X</strong> &nbsp;
    <img src="https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white" width="20%">
</p>

# About The Project
A Python version using Streamlit framework of the original <a href="https://github.com/theEmperorofDaiViet/eat-and-fit.git"><b>Eat & Fit</b></a> application - a simple <i>knowledge based system</i> using Fuzzy Logic to provide weight-loss guide consist of a diet plan and a workout plan based on user's current state.

> **Warning**: The diagnosis of body fatness and the weight-loss plan generated by this application is just imitation for programming purpose. You <b>should not</b> follow them. To get the right instructions, you should use actual weight-loss applications, or better yet, go to the doctor.

## Built With
* [![Python][Python-shield]][Python-url]
* [![Streamlit][Streamlit-shield]][Streamlit-url]
* [![NumPy][NumPy-shield]][NumPy-url]
* [![[Matplotlib]][Matplotlib-shield]][Matplotlib-url]
* [![Markdown][Markdown-shield]][Markdown-url]
* [![HTML5][HTML5-shield]][HTML5-url]
* [![CSS3][CSS3-shield]][CSS3-url]
* [![SQLite][SQLite-shield]][SQLite-url]
  

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Getting Started

## Prerequisites
Before cloning and using this application, you'll need to install these things on your computer:
* [Python 3.10.2](https://www.python.org/downloads/release/python-3102/): Streamlit is a app framework in Python language, so you need to have Python installed to run this application. I used Python 3.10.2, but I think it works fine with some other releases as well.
* [Visual Studio Code](https://code.visualstudio.com/download): You can choose any IDE or Text Editor that you want. To build a simple application like this, I recommend <b>Visual Studio Code</b>.
* [Streamlit](https://streamlit.io/): a free and open-source framework to rapidly build and share beautiful machine learning and data science web apps. Open the terminal and type this command to install Streamlit:
  ```sh
  pip install streamlit
  ```
* [NumPy](https://numpy.org/): a library for the Python programming language, adding support for large, multi-dimensional arrays and matrices, along with a large collection of high-level mathematical functions to operate on these arrays. Open the terminal and type this command to install Numpy:
  ```sh
  pip install numpy
  ```
* [Matplotlib](https://matplotlib.org/): a comprehensive library for creating static, animated, and interactive visualizations in Python. Open the terminal and type this command to install Matplotlib:
  ```sh
  pip install matplotlib
  ```
* [SQLite](https://sqlite.org/): a C-language library that implements a small, fast, self-contained, high-reliability, full-featured, SQL database engine. SQLite is the most used database engine in the world. SQLite is built into all mobile phones and most computers and comes bundled inside countless other applications that people use every day.
* [SQLiteStudio](https://sqlitestudio.pl/): a desktop application for browsing and editing SQLite database files. It is aimed for people, who know what SQLite is, or what relational databases are in general.

## Installation
You can install this application by cloning this repository into your current working directory:
```sh
git clone https://github.com/theEmperorofDaiViet/eat-and-fit.streamlit.git
```
After cloning the repository, you can open the project by Visual Studio Code. To run the application, open a terminal and type:
```sh
streamlit run eat_and_fit.py
```
As usual, the app should automatically open in a new tab in your browser. It runs on port 8501 by default.

Fast enough, huh? Let's stop for a while and take a look at the project's structure:

## Project Explorer

<table>
  <tr>
    <td><img src="/images/explorer.png" width="1600px"></td>
    <td>
      <p>
        The first subfolder, which named <b><i>algorithm</i></b>, is a package containing the algorithm used in the project. In this case, I used Fuzzy Logic, so there is a Python file named <code>fuzzy_logic.py</code> to implement it. I defined a rule table as a 2-dimensional numpy array and provided functions to perform each step of Fuzzy Logic: fuzzification, fuzzy inference and defuzzification. In each function, I put some <code>print()</code> functions to print the calculations. When running the app, you can see the results in the terminal.
      </p>
      <p>
        The second subfolder is <b><i>database</i></b>. The <code>eatandfit.db</code> file is the SQLite database of this application. You just need only it to use database in this app. But I still provided <code>.sql</code> files in the <b><i>scripts</i></b> subfolder to show the structure of each table in the database. You could modify these scripts and execute them to create another database that you want.
      </p>
      <p>
        The third subfolder, <b><i>images</i></b>, contains the images used in this application. I stored all images of dishes as <code>blob</code> type in the database and used <code>base64</code> to decode them back to <code>.jpg</code> images for  displaying. But I still provided them in the <b><i>dishes</i></b> subfolder for you to check.
      </p>
      <p>
        The fourth subfolder, which named <b><i>models</i></b>, is a package containing all the model class of this application. They are seperated into two <code>.py</code> files named <code>eat.py</code> and <code>fit.py</code>, respectively. The former  consists of all the classes needed to make a diet plan, and the latter consists of all the classes needed to make a workout plan.
      </p>
      <p>
        The final subfolder, which named <b><i>pages</i></b>, contains all <code>.py</code> files which will be loaded as pages by streamlit. Their names will be transformed to page names in the sidebar of the app.
      </p>
      <p>
        And the last thing to focus on is the <code>eat_and_fit.py</code> file. It is the "main" file of this application and will be loaded as the home page. That's why we type it's name in the command to run the app.
      </p>
    </td>
  </tr>
</table>

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Key Features
* Get and validate user input
* Process input by Fuzzy Logic to determine user's current state
* Provide a weight-loss plan based on user's state:
  * A diet plan consist of 3 different types of eating days per week: low, moderate and high carb
  * A workout plan of cardio and gym
* A "<b><i>eat</i></b>" page to search for food and recipe if the user want to know how to cook the dish in the diet plan.
* A "<b><i>fit</i></b>" page to search for exercise if the user want to know exactly how to do it.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# Usage
<i>This is a short video, which converted to gif, to illustrate the features of the application in a nutshell:</i>

<p align="center">
    <img src="/images/usage.gif">
</p>

- The home page includes a sidebar to navigate through other pages and enter input. The default input is male, 175 cm in height, 80 kg in weight and beginner.
- I change the weight to 50 kg and click the "<b><i>Submit</i></b>" button. My Fuzzy Logic considers a man with that height and weight to be "<i>underweight</i>". The application display a message to advise me to gain weight, not to lose weight.
- Then, I change the weight to 65 kg and click "<b><i>Submit</i></b>". My Fuzzy Logic considers a man with that height and weight to be "<i>normal</i>". The application display a message to advise me to maintain that healthy weight.
- This time I change the weight to 80 kg and click "<b><i>Submit</i></b>" again. My Fuzzy Logic considers a man with that height and weight to be "<i>overweight</i>". A message is displayed to inform my current state, and followed by the weight-loss plan provided for me.
- The plan consists of:
  - A diet plan with three menus for low, moderate, and high carb eating days. Each menu consists of nutrition info; a pie chart represent the percentage of calories from carbs, fat and protein; and dish for each meal.
  - A workout plan of cardio and gym.
- Then, I change the stage to "<i>intermediate</i>". You can see the plan is changed! Once the first plan is generated, you don't need to click the submit button, just change the input and the plan will be automatically changed according to the input you entered.
- After that, I navigate to the 🍱 <b><i>eat</i></b> page and search for a salmon recipe. There are several matched results, I choose <i>Roasted Salmon</i>. The page displays all about that recipe:
  - Dish's image
  - Nutrition info
  - Ingredients
  - Steps to cook
- Then, I navigate to the 🏋️‍♂️ <b><i>fit</i></b> page and search for an exercise for leg. There are several matched results, I choose <i>Leg Extension</i>. The page displays a video guide, overview and specific instructions to do the exercise.
- Finally, I go back to the home page. The input and the plan are still here! I used some workaround with <code>st.session_state</code> and callback to keep input value during navigating through other pages.

<p align="right">(<a href="#readme-top">back to top</a>)</p>

# References
I want to say a big thanks to [<b>Eat This Much</b>](https://www.eatthismuch.com/) and [<b>Muscle & Strength</b>](https://www.muscleandstrength.com/). I used some of their knowledge in diet and workout to build this project, but I also adjusted these knowledge a bit to match my programming idea. So, again:

> **Warning**: <b>DO NOT</b> trust in the plan in this application. You should go to [<b>Eat This Much</b>](https://www.eatthismuch.com/) and [<b>Muscle & Strength</b>](https://www.muscleandstrength.com/)'s website to see the <b>RIGHT</b> instructions.

# Contact
You can contact me via:
* [![GitHub][GitHub-shield]][GitHub-url]
* [![LinkedIn][LinkedIn-shield]][LinkedIn-url]
* ![Gmail][Gmail-shield]:&nbsp;<i>kumarankaruna66@gmail.com</i>
* [![Facebook][Facebook-shield]][Facebook-url]


<br/>
<p align="right">(<a href="#readme-top">back to top</a>)</p>

<!-- MARKDOWN LINKS & IMAGES -->
<!-- Tech stack -->
[Python-shield]: https://img.shields.io/badge/python-3670A0?style=for-the-badge&logo=python&logoColor=ffdd54
[Python-url]: https://www.python.org/
[Streamlit-shield]: https://img.shields.io/badge/Streamlit-FF4B4B?style=for-the-badge&logo=Streamlit&logoColor=white
[Streamlit-url]: https://streamlit.io/
[NumPy-shield]: https://img.shields.io/badge/numpy-%23013243.svg?style=for-the-badge&logo=numpy&logoColor=white
[NumPy-url]: https://numpy.org/
[Matplotlib-shield]: https://img.shields.io/badge/Matplotlib-%23ffffff.svg?style=for-the-badge&logo=Matplotlib&logoColor=black
[Matplotlib-url]: https://matplotlib.org/
[Markdown-shield]: https://img.shields.io/badge/Markdown-000000?style=for-the-badge&logo=markdown&logoColor=white
[Markdown-url]: https://www.markdownguide.org/
[HTML5-shield]: https://img.shields.io/badge/html5-%23E34F26.svg?style=for-the-badge&logo=html5&logoColor=white
[HTML5-url]: https://www.w3.org/html/
[CSS3-shield]: https://img.shields.io/badge/css3-%231572B6.svg?style=for-the-badge&logo=css3&logoColor=white
[CSS3-url]: https://www.w3.org/Style/CSS/
[SQLite-shield]: https://img.shields.io/badge/SQLite-07405E?style=for-the-badge&logo=sqlite&logoColor=white
[SQLite-url]: https://www.sqlite.org/index.html

<!-- Contact -->
[GitHub-shield]: https://img.shields.io/badge/github-%23121011.svg?style=for-the-badge&logo=github&logoColor=white
[GitHub-url]: https://github.com/KarunagaranR
[LinkedIn-shield]: https://img.shields.io/badge/linkedin-%230077B5.svg?style=for-the-badge&logo=linkedin&logoColor=white
[LinkedIn-url]:  https://www.linkedin.com/in/karunagaran-r-b25a94244/
[Gmail-shield]: https://img.shields.io/badge/Gmail-D14836?style=for-the-badge&logo=gmail&logoColor=white
[Facebook-shield]: https://img.shields.io/badge/Facebook-%231877F2.svg?style=for-the-badge&logo=Facebook&logoColor=white
[Facebook-url]: https://www.facebook.com/profile.php?id=100074460311320&mibextid=ZbWKwL
