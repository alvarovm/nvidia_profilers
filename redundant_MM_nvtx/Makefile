CUCOMP  = nvcc
CUFLAGS = -arch=sm_70

INCLUDES  = -I$(OMPI_DIR)/include -I$(OLCF_ESSL_ROOT)/include
LIBRARIES = -L$(OMPI_DIR)/lib -L$(OLCF_ESSL_ROOT)/lib64 -L$(CUDA_DIR)/lib64 -lmpi_ibm -lessl -lcublas -lnvToolsExt

redundant_mm: redundant_MM.o
	$(CUCOMP) $(CUFLAGS) $(LIBRARIES) redundant_MM.o -o redundant_mm

redundant_MM.o: redundant_MM.cu
	$(CUCOMP) $(CUFLAGS) $(INCLUDES) -c redundant_MM.cu

.PHONY: clean cleanall

clean:
	rm -f redundant_mm *.o

cleanall:
	rm -f redundant_mm *.o *.nvvp mat_mul*
