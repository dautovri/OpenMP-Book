# Векторизация

Использование **restrict**


```

#pragma omp simd 
#pragma omp declare simd
#pragma omp parallel for simd

  #pragma omp simd  safelen(длина)
                    linear(list[:шаг])
                    aligned(list[:alignment])
                    private(list)
                    lastprivate(list)
                    reduction(операция:list)
                    collapse(n)
                    
                    list - список переменных


```

Парадигма SIMD – single instruction multiple data (одна инструкция множество данных).

```
usingnamespace std;

int main()
{
const int SIZE = 300;
int x[SIZE];
int y[SIZE];
int z[SIZE];

// Initialize loop
for (int i=0; i

x[i] =i;

y[i] = i * 2;

z[i] = 0;

}

// Main loop

#pragma omp simd

for (int i=0; i

z[i] =x[i] + y[i];

}

return 0;

}
```
