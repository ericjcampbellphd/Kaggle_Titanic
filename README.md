# Kaggle_Titanic
Python code attempting to predict the <a href="https://www.kaggle.com/c/titanic/overview">survivors of the Titanic</a> using Machine Learning

Kaggle provides a train and test set with the following features:
<ul>
  <li>PassengerId (A unique value identifying the passenger)</li>
  <li>Pclass (The ticket class 1st/2nd/3rd)</li>
  <li>Name</li>
  <li>Sex (Male of Female)</li>
  <li>Age</li>
  <li>SibSp (Number of siblings or spouses aboard)</li>
  <li>Parch (Number of parents or children aboard)</li>
  <li>Ticket (Code number of the ticket)</li>
  <li>Fare</li>
  <li>Cabin (The deck and room number)</li>
  <li>Embarked (The port of emarkation for that passenger: C = Cherbourg, Q = Queenstown, S = Southampton)</li>
</ul>

The solution procedure is as follows:
<ul>
  <li>Name, Ticket, Cabin, and PassengerId are not used as features. Cabin may be used in a later merge because its deck may be a significant feature.</li>
  <li>Age, Embarked, and Fare are missing some data. The train set is grouped by Sex and Pclass, and Age and Fare are filled in based on the Pclass/Sex of the person.</li>
  <li>Embarked is filled in using the majority case (S = Southampton) where most people embarked from.</li>
  <li>A pipeline is built in which Pclass, Sex, Fare, and Embarked are OneHotEncoded, while Age and Fare are scaled by StandardScaler.</li>
  <li>A LogisticRegression model is implemented and optimized using GridSearchCv.</li>
 </ul>
 
 Submission on the test set produced a score of 0.76794
