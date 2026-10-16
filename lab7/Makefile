CC = mpicc
CFLAGS = -Wall -O2

EX1 = exercise01/sum_bcast
EX2 = exercise02/sum_scatter
EX3 = exercise03/sum_gather
EX4 = exercise04/sum_reduce
EX5 = exercise05/sum_allreduce
EX6 = exercise06/sum_scan

PROGS = $(EX1) $(EX2) $(EX3) $(EX4) $(EX5) $(EX6)

all: $(PROGS)

exercise01/sum_bcast: exercise01/sum_bcast.c
	$(CC) $(CFLAGS) -o $@ $<

exercise02/sum_scatter: exercise02/sum_scatter.c
	$(CC) $(CFLAGS) -o $@ $<

exercise03/sum_gather: exercise03/sum_gather.c
	$(CC) $(CFLAGS) -o $@ $<

exercise04/sum_reduce: exercise04/sum_reduce.c
	$(CC) $(CFLAGS) -o $@ $<

exercise05/sum_allreduce: exercise05/sum_allreduce.c
	$(CC) $(CFLAGS) -o $@ $<

exercise06/sum_scan: exercise06/sum_scan.c
	$(CC) $(CFLAGS) -o $@ $<

run: all
	@echo "--- Running all programs with 4 processes ---"
	@for p in $(PROGS); do \
		echo ">>> Running $$p <<<"; \
		mpirun --oversubscribe -np 4 ./$$p; \
		echo ""; \
	done

clean:
	rm -f $(PROGS)
