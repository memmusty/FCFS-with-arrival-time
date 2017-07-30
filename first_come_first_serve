
package first_come_first_serve;


 import java.util.*; 
public class First_come_first_serve 
{

    public static void main(String args[]) throws Exception 
    { 
        int jobs,ArrivalTime[],BurstTime[],WaitingTime[],TurnAroundTime[],ServiceTime[],Complete[]; 
        float AverageWaitingTime=0; 
        Scanner input=new Scanner(System.in); 
        System.out.print("Enter no of process: "); 
        jobs=input.nextInt(); //number of processes
        BurstTime=new int[jobs]; //burst time of processes
        WaitingTime=new int[jobs];  //waiting time of processes
        ServiceTime=new int[jobs+1];  //service time of processes
        Complete=new int[jobs]; //complete time of processes
        TurnAroundTime=new int[jobs]; //turnaround time of processes
        ArrivalTime=new int[jobs]; //arrival time of processes
        System.out.println("Enter Burst time for each process in ms\n=================================="
                + "============="); 
        for(int i=0;i<jobs;i++) 
        { //get processes burst time
            System.out.println("Enter Burst time for process "+(i+1)); 
            BurstTime[i]=input.nextInt(); 
        } 
        System.out.println("==============================================="); 
        System.out.println("Enter Arrival Time for each process in ms\n================================"
                + "==============="); 
        for(int i=0;i<jobs;i++) 
        { //get processes arrival time
            System.out.println("Enter Arrival Time for process "+i); 
            ArrivalTime[i]=input.nextInt();  
        }   
        System.out.println("===============================================");  
        ServiceTime[0]=0; 
        //to calculate waiting time
        for(int i=1;i<jobs;i++) 
        { 
            ServiceTime[i]=ServiceTime[i-1]+BurstTime[i-1];// Add burst time of previous processes
            WaitingTime[i]=ServiceTime[i]-ArrivalTime[i]; // Find waiting time for current process = 
                                                           //sum of burst time of previous processes - at[i]
        } 
        ServiceTime[jobs]=ServiceTime[jobs-1]+BurstTime[jobs-1]; 
        for(int i=0;i<jobs;i++) 
        { 
            TurnAroundTime[i]=WaitingTime[i]+BurstTime[i]; //time elapsed between arrival and completion
            Complete[i]= TurnAroundTime[i]+ArrivalTime[i]; //time the process complete execution
            AverageWaitingTime=AverageWaitingTime+WaitingTime[i]; 
        } 
        System.out.printf("%s%7s%10s%10s%7s%12s%12s\n","Process","Burst","Arrival","Service","Wait","TurnAround",
                "Completion"); 
        for(int i=0;i<jobs;i++) 
        {
            System.out.printf("%5d%7d%10d%10d%7d%10d%12d\n",i,BurstTime[i],ArrivalTime[i],ServiceTime[i],
                    WaitingTime[i],TurnAroundTime[i],Complete[i]);
        } 
        AverageWaitingTime=AverageWaitingTime/jobs; //i.e total_wait_time/no_of_jobs
        System.out.println("===============================================");  
        System.out.println("    The Average Waiting Time = "+AverageWaitingTime+"ms"); 
        System.out.println("===============================================");
        System.out.println("Gantt Chart");
        for(int i=0;i<jobs;i++) 
        { //prints Gantt chart
            System.out.printf("%d--P%d--",ServiceTime[i],i);
        }
        System.out.println(ServiceTime[jobs]);
    } 
} 
