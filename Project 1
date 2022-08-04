#include <iostream>
using namespace std;

class CRM
{
protected:
    int n; //The number rows of the original matrix
    int m; //The number of columns of the original matrix
    int nonZeros; //The number of non-zero elements in the original matrix
    int* values; //Array that contains all non-zero values of the matrix, assuming they are all integers
    int* rowPos; //Array that for each row of the original matrix contains the position in the values matrix in which the first non-zero element of this row is stored.
    int* colPos; //Array that contains the column number for each one of the non-zero values in the original matrix.
    //There may be others you may need
public:
    CRM ( ); //default or empty constructor
    CRM (int rows, int cols, int numNonZeros);
    int incrementRow = 0; // incrementer for row
    int incrementValue = 0;// incrementer for value
    int incrementCol = 0; // incrementer for column
    int tracker = 0; // used for counting in rowPos and assigning row variables
    int userRetweets = 0; // tracks number of tweets being added at an element
    int getNumRows ( );
    void addValue (int value); //add a new value in the values array
    void addRow (int row); //add a row number in the rowPos array
    void addColumn (int col); //add a column number in the colPos array
    void display (); /*print the contents of the three arrays. Each array must be on a different line (separated by a
    new line character) and you have exactly a single space between each value printed. */
    int mostInfluentialUser(); //find the most influential user
    int mostActiveUser(); //find the most active user
    int* mostInfluential;
    int* influentialUsers (); //compute vector of users ranked by how much influential they are
    int* activeUsers (); //compute vector of users ranked by how much active they are
    ~CRM(); //destructor
    //You may define and use any other method you need
    void sortMethod(int* a, int* b); // sort for influential
    void sortInfluential(int *a, int *b);
};

//some methods – Katia Papakonstantinopoulou

CRM::CRM ( ) // general constructor for variables in array;
{
    n = 0;
    m = 0;
    incrementRow = 0;
    tracker = 0;
    values = NULL;
    rowPos = NULL;
    colPos = NULL;
    mostInfluential = NULL;
}
CRM::CRM (int rows, int cols, int numNonZeros) // constructor to initialize in main what shape our CRM will take
{
    n = rows;
    m = cols;
    nonZeros = numNonZeros;
    values = new int[nonZeros];
    rowPos = new int[n];
    colPos = new int[nonZeros];
    mostInfluential = new int[n];
}
int CRM::getNumRows()
{
    return n; // simple getter that returns n, which is the inputted number of rows
}
void CRM::addValue(int value)  //add a new value from the file in the values array
{
    values[incrementValue] = value;
            incrementValue++; // adds the values of input from the file into a new element of the array
        //same as column
}
void CRM::addRow(int row) //add a row number in the rowPos array
{
    if(row == 0 && incrementRow == 0) // for first index we must set first value equal to zero so that way we can compare all values after and see what is stored starting at element 0
    {
        rowPos[incrementRow] = 0;
    }

    if (row > (incrementRow + 1))  // if we go through that file and find out that there is a row with no values we assign that index to -1
    {
        incrementRow++;
        rowPos[incrementRow] = - 1;
    }
    if (row == incrementRow) // this is a counter for us to see duplicates
    {
        tracker++;
    }
    else //if the next value in the file is an increased number we know its a later row
    {
        incrementRow++;
        rowPos[incrementRow] = tracker;
        tracker++; // increments current tracker and assigns the value of rowPos to the value of tracker that hasnt been put in the array yet
    }
}
void CRM::addColumn(int col) //add a column number in the colPos array
{
        colPos[incrementCol] = col;
            incrementCol++; // adds the column number of input from the file into a new element of the array
}
void CRM::display()//print the contents of the three arrays. Each array must be on a different line (separated by a
//new line character) and you have exactly a single space between each value printed.
{
    cout << "values: "; // these 3 loops are indentical but must be seperate or else the lines would be mixed up between values,rows, and cols
    for(int i = 0; i < nonZeros; i++) {
       cout << values[i] << " ";
    }

    cout << "\n" << "rowPos: "; // prints rowPos values
    for(int i = 0; i < getNumRows(); i++) {
        cout << rowPos[i] << " ";
    }

    cout << "\n" << "colPos: " ; // prints colPos in order they were stored
    for(int i = 0; i < nonZeros; i++) {
        cout << colPos[i] << " ";
    }
cout << "\n";
}
int CRM::mostInfluentialUser() //find the most influential user
{
    int* mostInfluential = influentialUsers(); // creates a new array and calls the method to sort it from highest retweets to least
    return mostInfluential[0]; // this is the value with the most amount of retweets according to the sort/and influential user methods
}

int CRM::mostActiveUser() //find the most active user
{
/*    int mostActiveUser = 0; // placeholder integer but needs to increment through the rows and add the values to see who has retweeted the most times
    for(int j = 0; j < n; j++) {
        userRetweets = 0;

        for (int i = 0; i < nonZeros; i++) {
            if (rowPos[j] == i) {
                userRetweets += values[i];
            }
            if (userRetweets > mostActiveUser) {
                mostActiveUser = userRetweets;
                mostActiveUser = j;
            }
        }
    }
    return mostActiveUser;// user who has retweeted the most amount of tweets*/
int* mostActive = activeUsers();
return mostActive[0];
}

void CRM::sortMethod(int* a, int* b)  {  //Sort swapping array values and indexes
    int joint[n][2];
    for(int i = 0; i < n; i++)  {
        for(int j = i + 1; j < n - i - 1; j++) {
            if(a[j] > a[i]) {
                joint[a[j]][b[i]];
                int subB = b[i]; //stores variable for b[i]
                int subA = a[i]; //stores variable for a[i]
                b[i] = b[j]; // takes value at increased index
                a[i] = a[j];
                b[j] = subB; //takes the index from value just shifted and replaces it with stored value
                a[j] = subA;
                //a = joint[][i];
            }
        }
    }
}

void CRM::sortInfluential(int* a, int* b)  {  //Sort swapping array values and indexes
    //int joint[n][2];
    for(int i = 0; i < n; i++)  {
        for(int j = i + 1; j < n - i - 1; j++) {
            if(b[j] > b[i]) {
                //joint[a[j]][b[i]];
                int subB = b[i]; //stores variable for b[i]
                int subA = a[i]; //stores variable for a[i]
                b[i] = b[j]; // takes value at increased index
                a[i] = a[j];
                b[j] = subB; //takes the index from value just shifted and replaces it with stored value
                a[j] = subA;
                //a = joint[][i];
            }
        }
    }
}

int* CRM::influentialUsers () //compute vector of users ranked by how much influential they are
{
    int* output = new int[n]; // uses columns to look through how many retweets each user has had and ranking them from the most times they have been retweeted to the least

    for(int i = 0; i < n; i++) { // creates an array with values 1-n
        output[i] = i;
    }
    int* tempArray = new int[n]; // this will store the number of retweets
        for (int j = 0; j < n; j++)
        {
            userRetweets = 0; // always reset retweets back to zero so when we go to next row/col it changes
            for(int k =0; k < nonZeros; k++) {
                if (j == colPos[k]) {
                    userRetweets += values[k];
                }
            }
            tempArray[j] = userRetweets;
        }
        sortInfluential(output, tempArray); // calls sort method to sort arrays and return most influential users numbers
    return output;
}

int* CRM::activeUsers() //compute vector of users ranked by how much active they are
{
    int* activeUsers = new int [n];
    for(int i = 0; i < n; i++) //Assigns zero to all elements in the array
    {
        activeUsers[i] = i;
    }
    int* retweetNumbers = new int[n]; // array that keeps track of how many retweets there were
    int counter = 0;
    int row = 1;
    for (int j = 0; j < nonZeros; j++) {
        if (j == rowPos[row]) {
            if (row > counter + 1) {
                counter++;
                retweetNumbers[counter] = 0;
            }
            counter++;
            row++;
        }
        else if (rowPos[row] == -1) {   // if rowPos == -1, then we know we can skip row because that row had no nonZero values on those rows
            row++;
        }
        retweetNumbers[counter] += values[j]; //accumulates and adds retweets from the values array together until totals are calculated
    }
    sortMethod(retweetNumbers, activeUsers); // calls sort method to count values and print the users in order of activity
    return activeUsers;
}

CRM::~CRM ( ) // Destructor to save space in the program by eliminating class specific variables.
{
    if (values != NULL) delete [ ] values;
    if (rowPos != NULL) delete [ ] rowPos;
    if (colPos != NULL) delete [ ] colPos;
    cout << "CRM Object Destroyed!!" << endl;
    m;
    nonZeros;
}

#include <iostream>
using namespace std;
//write the entire CRM class here with all the methods

int main ( )
{
    CRM * A;
    int numRows, numColumns, numNonZeros; // crm variables that will be filled by the user variables
    int row, col, value; // user entered variables

    //read in the first matrix
    cin >> numRows >> numColumns; //line 1 of input
    cin >> numNonZeros; //line 2 of input
    A = new CRM (numRows, numColumns, numNonZeros);
     for (int i = 0; i < numNonZeros; i++) { // numNonZeros + 1 is placeholder
        cin >> row >> col >> value;
        (*A).addValue (value);
        (*A).addRow (row);//needs to be done cleverly in the method
        (*A).addColumn (col);
    }

    (*A).display ( );

//Find most influential user
    int mostInf = (*A).mostInfluentialUser ();
    cout << "\n" << "Most influential user: " << mostInf << endl;
    cout << endl;

//Find most active user
    int mostAct = (*A).mostActiveUser(); // call most active method to print who is most active
    cout << "Most active user: " << mostAct << endl;
    cout << endl;

//Rank users based on how much influential they are
    int* influentialityVector = (*A).influentialUsers (); // prints users in order from most influential to least according to number of retweets
    cout << "Users ranked by Influentiality: " ;
    for (int i=0; i < (*A).getNumRows(); i++)
        cout << influentialityVector [i] << " ";
    cout << endl << endl;

//Rank users based on how much active they are
//fill-in code
int* activeVector = (*A).activeUsers();
    cout << "Users ranked by Activity: " ;
    for (int i=0; i < (*A).getNumRows(); i++)
        cout << activeVector[i] << " "; // this should print all users with a space between
        // this will probably print the contents of an array tracking how many retweets were performed
    cout << endl;

// Call the destructors
    delete A;
    delete [ ] influentialityVector; //originally influentialVector
    //delete ___;

    return 0;
}
