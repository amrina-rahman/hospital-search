# hospital-search
#include<stdio.h>
#include<string.h>
//Structure for Patient recprd
struct Patient
{
    int id;
    char name[20];
    char phone[15];
};
//Linear search function
int linearSearch(struct Patient patients[], int size, int target_id){
    for(int i = 0; i< size ; i++){
        if(patients[i].id == target_id){
        return i;
    }
    }
    return -1;
}

int main(){
    // list of admitted patients
    struct Patient patients[]={
        {101, "Adiba Rahman", "01234567891"},
        {102, "Amrina Rahman", "0161706266"},
        {103, "Al Jubair", "01680074257"},
        {104, "Tasnim Gazi","01011121314"},
        {105, "Md.Shopnil", "01151617181"}
    };
    int totalpatient = sizeof(patients)/sizeof(patients[0]);
    int search_id;
    //search patient
    printf("Enter Patient ID to Search: ");
    scanf("%d", &search_id);
    int result = linearSearch( patients, totalpatient, search_id);
    if( result== -1){
        printf("The patient has no Records.");
    }
    else{ 
        printf("Patient is Found!!\n");
        printf(" Patient's ID: %d\n" , patients[result].id);
        printf(" Patient's Name: %s\n" , patients[result].name);
        printf(" Patient's Phone No.: %s" , patients[result].phone);
    }
    return 0;
}
