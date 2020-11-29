# circular-queue
#include<stdio.h>
#include<stdlib.h>
#define N 6
int rear=-1,front=-1;
int q[N];
void insert(int x){
	if(front==-1 && rear==-1){
		front=rear=0;
		q[rear]=x;
		printf("%d is Inserted\n",x);
	}else if((rear+1)%N==front) {
		printf("Queue is full\n");
		
	}else{
		rear=(rear+1)%N;
		q[rear]=x;
		printf("%d is Inserted\n",x);
	}
	
}
void delet(){
	if(front==-1 && rear==-1){
		printf("Queue is underflow\n");
	} else if(front==rear){
		printf("%d is deleted\n",q[front]);
		front=rear=-1;
		
	}else{
		printf("%d is deleted\n",q[front]);
		front=(front+1)%N;
		
	}
}
void display(){
	int i=front;
		if(front==-1 && rear==-1){
		printf("Queue is underflow\n");
	}else{
		printf("Queue is...............\n");
		while(i!=rear){
			printf("%d",q[i]);
			i=(i+1)%N;
		}
		printf("%d",q[rear]);
	}
}
int main(){
	int c,z;
	while(1){
	printf("\n1.Insert || 2. Delete || 3. Display || 4. Exit\n");
	printf("Enter Your choice\n");
	scanf("%d",&c);
		switch(c){
			case 1:	printf("Enter a number\n");
					scanf("%d",&z); 
					insert(z);
					break;
			case 2:delet();
					break;
			case 3:display();
					break;
			case 4: exit(1);
			
			default:printf("Wrong choice\n");
										
		}
	}
	return 0;
}
