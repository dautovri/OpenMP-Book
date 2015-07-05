# SIMD

##### *Я не могу долго быть одна. Когда я одна — я ничто. Просто набор скверных качеств.*
######Эрих Мария Ремарк "Земля обетованная"

Парадигма SIMD – single instruction multiple data (одна инструкция множество данных).
```
#pragma omp simd 
```
Клаузы:
* safelen(длина)
* linear(список[:шаг])
* aligned(список[:выравнивание])
* private(список)
* lastprivate(список)
* reduction(операция:список)
* collapse(n)


```
void star( double *a, double *b, double *c, int n, int *ioff )
{
    int i;
    #pragma omp simd
    for ( i = 0; i < n; i++ )
    a[i] *= b[i] * c[i+ *ioff];
}

```


---


```
#pragma omp declare simd
```

Клаузы:
* simdlen(длина)
* linear(список[:шаг])
* aligned(список[:выравнивание])
* uniform(список)
* inbranch
* notinbranch

```
#pragma omp declare simd
float foo(float *B, float *C, int i)
{
	return B[i] + C[i];
}
for( i=0 ; i < N ; i++ )
{
	A[i] = foo(B, C, i);
}

```


---

```
#pragma omp parallel for simd
```

Пример применения **simd** к циклу:
```
  #pragma omp parallel for simd
  for (i=0; i<N; i++) 
  { 
    a[i] = b[i] * c[i]; 
  }

```

