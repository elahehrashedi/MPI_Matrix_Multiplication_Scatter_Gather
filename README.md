# MPI_Matrix_Multiplication_Scatter_Gather
Matrix Multiplication using collective communication routines, such as scatter, gather, and allgather, whenever possible.

The basic problem is almost the same as "https://github.com/elahehrashedi/MPI_Matrix_Multiplication" project. However, there are two differences:

(1) Using collective communication routines, such as scatter, gather, and allgather,
whenever possible.
(2) To measure the execution times and study the scalability of the programs and
your system.

You can use this routine (double MPI_Wtime(void)) to get the number of seconds that
have elapsed since an arbitrary time in the past. To time some parallel computation, do:

	MPI_Barrier(MPI_COMM_WORLD); /* barrier is needed if no necessary
	synchronization for the timing is ensured yet */
	double start = MPI_Wtime(); /* only 1 process needs to do this */
	/* the work to be timed */
	MPI_Barrier(MPI_COMM_WORLD); /* barrier is needed if no necessary
	synchronization for the timing is ensured yet */
	double end = MPI_Wtime(); /* only 1 process needs to do this */
	
Then the time elapsed for the execution is (end – start). Don’t include the time for reading file in the measurement.