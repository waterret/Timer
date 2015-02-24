# Timer
A simple but powerful C++ code performance measurement library which just contains a single header file.

Simple example within the timer.h file

inline void* time_malloc(size_t size) {
  TIMER_FLOPS("time_malloc", size);
  void* p = malloc(size);
  memset(p, 0, size);
  return p;
}

inline void time_free(void* ptr) {
  TIMER("time_free");
  free(ptr);
}

#define malloc(x) time_malloc(x)

#define free(x) time_free(x)
