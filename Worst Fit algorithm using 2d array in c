#include <stdio.h>
int main()
{	
    int no_of_partitions, no_of_processes;
    int max_partition_size = 0;
    int MAX_PARTITIONS = 10;
    int MAX_PROCESSES = 10;
    int PARTITION_FIELDS = 3;
    int PROCESS_FIELDS = 2;
	
    printf("Enter the number of partitions : ");
    scanf("%d", &no_of_partitions);
    printf("Enter the number of processes : ");
    scanf("%d", &no_of_processes);
	
    int partitions[MAX_PARTITIONS][PARTITION_FIELDS];
    int processes[MAX_PROCESSES][PROCESS_FIELDS];
	
    //take partition and process details from user
    int i, j;
    for(i = 0; i < no_of_partitions; i++)
    {
        printf("Enter the id, size and availability of partition %d: ", i+1);
        for(j = 0; j < PARTITION_FIELDS; j++)
        {				
            scanf("%d", &partitions[i][j]);
        }
    }
    for(i = 0; i < no_of_processes; i++)
    {
        printf("Enter the id and size of process %d: ", i+1);
        for(j = 0; j < PROCESS_FIELDS; j++)
        {				
            scanf("%d", &processes[i][j]);
        }
    }
	
    //worst fit algorithm
    for(i = 0; i < no_of_processes; i++) //to iterate all process
    {
        max_partition_size = 0;
        int max_partition_index = -1;
        for(j = 0; j < no_of_partitions; j++)
        {
            if(partitions[j][PARTITION_FIELDS-1] == 0 && partitions[j][PARTITION_FIELDS-2] >= processes[i][PROCESS_FIELDS-1])
            {
                if(partitions[j][PARTITION_FIELDS-2] > max_partition_size)
                {
                    max_partition_size = partitions[j][PARTITION_FIELDS-2];
                    max_partition_index = j;
                }
            }
        }
        
        //to set the avaiability flag as allocated i.e.changing status from 0 to 1
        if(max_partition_index != -1)
        {
            partitions[max_partition_index][PARTITION_FIELDS-1] = 1;
        }
    }
    
    //to print the end result
    printf("\nProcesses\n");
    for(i = 0; i < no_of_processes; i++)
    {
        for(j = 0; j < PROCESS_FIELDS; j++)
        {				
            printf("%d\t", processes[i][j]);
        }
        printf("\n");
    }
   	
	printf("\nPartitions\n");
     for(i = 0; i < no_of_partitions; i++)
    {
        for(j = 0; j < PARTITION_FIELDS; j++)
        {				
            printf("%d\t", partitions[i][j]);
        }
        printf("\n");
    }
}
