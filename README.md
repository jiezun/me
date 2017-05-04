# me
#include<iostream>

using namespace std;

class Matrix
{
private:
	int line1, line2;
    int column;
	int matrix1[50][100];
	int matrix2[50][50];
public:
	Matrix();
	friend Matrix & operator+();
	friend Matrix & operator-();
	friend Matrix & operator--();
};

Matrix::Matrix()
{
	cout<<"please enter the line and the column:"<<endl;
	cin>>line1>>column;
	cout<<"please enter the matrix:"<<endl;
	for(int j = 0; j < line1; j++)
	{
    	for(int i = 0; i < column; i++)
		{
        	cin>>matrix1[i][j];
		}
	}
	cout<<endl<<"please enter the line of another matrix:"<<endl;
	cin>>line2;
	cout<<"please enter the matrix:"<<endl;
	for(int j = 0; j < line2; j++)
	{
    	for(int i = 0; i < column; i++)
		{
        	cin>>matrix2[i][j];
		}
	}
}

Matrix & operator+()
{
	for(int i = 0; i < line2; i++)
	{
		for(int j = 0; j < column; j++)
		{
			if(matrix2[i][j] != matrix1[i][j])
			{
				for(int k = 0; k < column; k++)
				{
					matrix1[line+i][k] = matrix2[line+i][k];
				}
			}
		}
	}
}

Matrix & operator-()
{
	for(int i = 0; i < line2; i++)
	{
		for(int j = 0, n = 0; j < column; j++)
		{
			if(matrix2[i][j] != matrix1[i][j])
				break;
			else
				n++;
			if(n == column)
			{
				for(int k = i+1; k < line; k++)
				{
					for(int h = 0; h < column; h++)
					{
						matrix1[k][h] = matrix1[k][h]
					}
				}
			}
		}
	}
}

int main()
{
	Matrix c1, c2;
	c1 = c1 + c2;
	return 0;
}
