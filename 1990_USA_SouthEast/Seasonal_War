// Problem URL: https://icpcarchive.ecs.baylor.edu/external/52/5246.pdf

#include <iostream>
#include <vector>

using namespace std;

int kill_war_eagle(char * * array, int i, int j)
{ 
    if (array[i][j] == '0')
    {
        return 0; 
    }
    array[i][j] = '0';
    kill_war_eagle(array, i-1, j-1);  
    kill_war_eagle(array, i-1, j);
    kill_war_eagle(array, i-1, j+1);
    kill_war_eagle(array, i, j-1);
    kill_war_eagle(array, i, j+1);
    kill_war_eagle(array, i+1, j-1);  
    kill_war_eagle(array, i+1, j);
    kill_war_eagle(array, i+1, j+1);
    return 1; 
}

char * * read_in_new_array(int n)
{ 
    int i, j;
    char * * array;
    array = new char * [n+2];
    for (i = 0; i < n+2; i+=1)
    {     
        array[i] = new char[n+2];  
    }
    for (i = 0; i < n; ++i)
    { 
        array[0][i]   = '0';
        array[n-1][i] = '0';
        array[i][0]   = '0';
        array[i][n-1] = '0'; 
    }
    for (i = 1; i < n-1; ++i)
    {
        for (j = 1; j < n-1; ++j)
        {
            cin >> array[i][j];
        }
    }    
    return array; 
}    

void free_array(char * * array, int n)
{ 
    int i, j;
    for (i = 0; i < n; i += 1)
    {  
        delete [] array[i];
    }
    delete [] array; 
}

void print_war_eagle(char * * array, int n)
{ 
    int i, j;
    cout << endl;
    for (i = 0; i < n; ++i)
    { 
        cout << endl;
        for (j = 0; j < n; ++j)
        {
            cout << array[i][j]; 
        }
    } 
}

int number_of_war_eagles()
{ 
    int i, j, n, number_of_eagles = 0;
    cin >> n;
    if (cin.fail())
    {    
        return -1;
    }
    n += 2;
    char * * array = read_in_new_array(n);
    for (i = 1; i < n-1; ++i)
    {
        for (j = 1; j < n-1; ++j)
        {      
            if (kill_war_eagle(array, i, j))
            {
                number_of_eagles += 1;
            }
        }
    }
    free_array(array, n);
    return number_of_eagles;
}

int main()
{ 
    int i, n;
    n = number_of_war_eagles();
    for (i = 1; n >= 0; i += 1)
    { 
        cout << "Image number " << i << " contains ";
        cout << n << " war eagles." << endl;
        n = number_of_war_eagles(); 
    }
    return 0; 
}
