1. 参见教材P96任务5.2。


2.
[这篇博客](https://www.cnblogs.com/CXCXCXC/p/4641812.html)


3.
```c
#include <stdio.h>
int main() {
	char str[20];
	char spell[][5] = {"ling", "yi", "er", "san", "si",
	                   "wu", "liu", "qi", "ba", "jiu"
	                  };
	int i = 0;
	scanf("%s", str);
	if (str[i] == '-') {
		printf("fu ");
		++i;
	}
	for ( ; str[i]; ++i) {
		printf("%s", spell[str[i] - '0']);
		if (str[i + 1])
			printf(" ");
	}
	return 0;
}
```

4.
```c
#include <stdio.h>
#include <math.h>
int main() {
	int n;
	int i, temp;
	int flag = 0;
	scanf("%d", &n);
	for (i = 1; i <= n; ++i) {
		temp = (int)sqrt(n - i * i);
		if (i > temp)
			break;
		if (i * i + temp * temp == n) {
			printf("%d %d\n", i, temp);
			flag = 1;
		}
	}
	if (flag == 0)
		printf("No Solution");
	return 0;
}
```

5.
```c
#include <stdio.h>
#include <string.h>
int main() {
	char str[1000];
	int len;
	int arr[100];
	int i = 0, j;
	while (1) {
		scanf("%s", str);
		len = strlen(str);
		if (str[len - 1] != '.')
			arr[i++] = len;
		else {
			if (len != 1)
				arr[i++] = len - 1;
			break;
		}
	}
	for (j = 0; j < i; ++j) {
		printf("%d", arr[j]);
		if (j != i - 1)
			printf(" ");
	}
	return 0;
}
```

6.
```c
#include <stdio.h>
#include <string.h>
int main() {
	int a, b, c;
	scanf("%d%d%d", &a, &b, &c);
	if (a == b)
		printf("C");
	else if (a == c)
		printf("B");
	else
		printf("A");
	return 0;
}
```

8
```c
#include <stdio.h>
const int N = 13;
int arr[N] = {0};
void PascalTriangle(int row) {
	if (row == 1) {
		arr[1] = 1;
		printf("%6d\n", arr[1]);
		return;
	}
	PascalTriangle(row - 1);
	for (int i = row; i >= 1; --i)
		arr[i] += arr[i - 1];
	for (int i = 1; i <= row; ++i)
		printf("%6d", arr[i]);
	printf("\n");
}
int main() {
	PascalTriangle(N);
	return 0;
}
```
