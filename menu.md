//This is done by sumo::
#include<iostream>
using namespace std;

void insert(int arr[],int size){
    cout<<"Enter the Element of Array:\n"<<endl;
    for(int i=0;i<size;i++)
    {
    cin>>arr[i];
    }
    cout<<"Arrays={";
    for(int i=0;i<size;i++){
        if(i==size-1){
            cout<<arr[i];
        }
        else{
            cout<<arr[i]<<" ,";
        }
    }
    cout<<"}\n";
}
void del(int arr[], int& size) {
    int delIndex;
    cout << "Enter the index to delete:";
    cin >> delIndex;
    for(int i=0;i<size-1;i++){
        if(i<delIndex){
            cout<<arr[i]<<" ";
        }
        else{
            cout<<arr[i+1]<<" ";
             }
        }
    }

void search(int arr[],int size){
    int n;
    cout<<"Enter the number do you want to search:"<<endl;
    cin>>n;
    bool found=false;
    for(int i=0;i<size;i++){
        if(arr[i]==n){
            cout<<"The searching element is :"<<arr[i];
            found=true;
            break;
        }
    }
    if(!found){
        cout<<"A.The searchig element is not found:"<<endl;
    }
}

void sort(int arr[],int size){
    for(int i=0;i<size-1;i++){
        for(int j=i+1;j<size;j++){
            if(arr[i]>arr[j]){
                int temp=arr[i];
                arr[i]=arr[j];
                arr[j]=temp;
            }
        }
    }
    cout<<"Sorted Arrays:{";
    for(int i=0;i<size;i++){
        if(i==size-1){
            cout<<arr[i];
        }
        else{
            cout<<arr[i]<<" ,";
        }
    }
    cout<<"}.";
}

void merge(int arr1[],int size1,int arr2[],int size2){
   int  mergesize=size1+size2;
    int mergearr[mergesize];
    for(int i=0;i<size1;i++){
        mergearr[i]=arr1[i];
    }
    for(int i=0;i<size2;i++){
        mergearr[size1+i]=arr2[i];
    }
    cout<<"Display Merging arrays:{";
    for(int i=0;i<mergesize;i++){
        if(i==mergesize-1){
            cout<<mergearr[i];
        }
        else{
            cout<<mergearr[i]<<",";
        }
    }
    cout<<"}.";
}

void display(int arr[],int size){
    cout<<"Arrays={";
    for(int i=0;i<size;i++){
        if(i==size-1){
            cout<<arr[i];
        }
        else{
            cout<<arr[i]<<",";
        }
    }
    cout<<" }.\n";
}

int main(){
    int options;
    int arr[4];
    //create 2 array for merge
    int arr1[4];
    int arr2[4];
    int size=4;
    int size1=4;
    int size2=4;
    cout<<"\t\tCreates array and do following task: \t"<<endl;
    jump:
    while(true){
        cout<<"\n\n\tDisplay menu\t"<<endl;
        cout<<"\t1.Insert: "<<endl;
         cout<<"\t2.Delete: "<<endl;
          cout<<"\t3.search: "<<endl;
           cout<<"\t4.sort: "<<endl;
           cout<<"\t5.Merge two array: "<<endl;
            cout<<"\t6.Display: "<<endl;
              cout<<"\t7.continue: "<<endl;
               cout<<"\t8.Exit: "<<endl;
               cout<<endl;
               cout<<"Enter your options:"<<endl;
               cin>>options;
               
               switch(options){
                   case 1:
                   insert(arr,size);
                   break;
                   
                   case 2:
                   del(arr,size);
                   break;
                   
                   case 3:
                   search(arr,size);
                   break;
                   
                   case 4:
                   sort(arr,size);
                   break;
                   
                   case 5:
                   cout<<"Enter the first merging array:"<<endl;
                   insert(arr1,size1);
                     cout<<"Enter the second merging array"<<endl;
                   insert(arr2,size2);
                   
                   merge(arr1,size1,arr2,size2);
                   break;
                   
                   case 6:
                   display(arr,size);
                   break;
                   
                   case 7:
                   cout<<"Continue the process:";
                   for(int i=3;i<size;i++){
                       goto jump;
                   }
                   break;
                   
                   case 8:
                   cout<<"Exit the program:"<<endl;
                   break;
                   
                   default:
                   cout<<"Envalid option:";
                   
               }
               
        
    }
    return 0;
}
