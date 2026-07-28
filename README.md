#include<iostream>
using namespace std;
int partition(int arr[],int low,int high){
int pivot=arr[high];
int i=low-1;
for(int j=low;j<high;j++){
    if(arr[j]<pivot){
        i++;
        swap(arr[i],arr[j]);
    }
}
    swap(arr[i+1],arr[high]);
    return i+1;
}
void quicksort(int arr[],int low,int high){
    if(low<high){
        int pi=partition(arr,low,high);
        quicksort(arr,low,pi-1);
        quicksort(arr,pi+1,high);
    }
}
int main(){
    int n;
    cout<<"enter no of elements";
    cin>>n;
    int arr[n];
    cout<<"array elements";
    quicksort(arr,0,n-1);
    for(int i=0;i<n;i++){
        cin>>arr[i];
    }
    cout<<"sorted array:";
    for(int x:arr){
        cout<<x<<" ";
    }
    return 0;
}
