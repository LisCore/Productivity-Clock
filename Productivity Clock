#include <iomanip>
#include <iostream>
#include <string>
#include <cmath>

using namespace std;

void welcome();
int numberTasks();
string taskContents(int i);
void getHours(int i, string contentList[], int &hours, int &minutes);
void calcHoursMins(int &totalHours, int &totalMinutes);

const int LIST_TASKS = 100;
const string ORDER_TASKS[10] = {"First", "Second", "Third", "Fourth", "Fifth", "Sixth", "Seventh", "Eighth", "Ninenth", "Tenth"};
const int HOURS = 60;
const int MINUTES = 60;

int main() {
  int taskList = 0;
  int i = 0;
  int hours = 0, minutes = 0;
  int totalHours = 0;
  int totalMinutes = 0;
  string contentList[LIST_TASKS]; 
  
  welcome();
  taskList = numberTasks();
  for (i = 0; i < taskList; ++i) {
    contentList[i] = taskContents(i);
    getHours(i, contentList, hours, minutes); 
    totalHours += hours;
    totalMinutes += minutes;
  }
  calcHoursMins(totalHours, totalMinutes);
  cout << "You completed " << totalHours << " hours and " << totalMinutes << " minutes! Keep on going!"; 
  
  return 0;
}
void welcome() {
  cout << "Welcome to the productivity clock." << endl;
  cout << "Please input the amount of tasks you completed today" << endl; 
  cout << "and I will calculate how many hours/minutes you spent being productive. \n" << endl;
}
int numberTasks() {
  int numObjective = 0;
  cout << "Please enter the number of objectives completed today: ";
  cin >> numObjective;
  while (numObjective < 0 || !cin) {
    cin.clear(); 
    cin.ignore(100, '\n'); 
    cout << "Invalid response, try again!" << endl;
    cout << "Please enter the number of objectives completed today: "; 
    cin >> numObjective;
  }
  cin.clear();
  cin.ignore(100, '\n');
  return numObjective;
}
string taskContents(int i) {
  string userInput;
  cout << "\nPlease enter the " << ORDER_TASKS[i] << " task completed: ";
  getline(cin, userInput);
  return userInput; 
}
void getHours(int i, string contentList[], int &hours, int &minutes) {
  cout << "How many hours and minutes did you spend on your " << ORDER_TASKS[i] << " task: " << contentList[i] << endl;
  cout << "Enter hours with a space then minutes" << endl;
  cin >> hours >> minutes;
  while (!cin || hours < 0 || hours > 24) {
    cout << "Invalid input, ensure hours is less than 24 hours." << endl;
    cout << "How many hours did you spend on your " << ORDER_TASKS[i] << " task: " << contentList[i] << endl;
    cin.clear();
    cin.ignore(100, '\n');
    cin >> hours;
  }
  while (!cin || minutes < 0 || minutes > 60) {
    cout << "Invalid input, ensure hours is less than 60 minutes." << endl;
    cout << "How many minutes did you spend on your " << ORDER_TASKS[i] << " task: " << contentList[i] << endl;
    cin.clear();
    cin.ignore(100, '\n');
    cin >> minutes;
  }
}
void calcHoursMins(int &totalHours, int &totalMinutes) {
  while (totalMinutes > 60) {
    totalMinutes %= 60;
    totalHours += 1;
  }
}