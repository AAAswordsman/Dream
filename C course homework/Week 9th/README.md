# 教授的课（程序设计基础第9周编程1）
### 描述

教授正在为一个有N个学生的班级讲授离散数学课。他对某些学生缺乏纪律性很不满意，于是决定：如果课程开始后上课的人数小于K，就取消这门课程。

从键盘输入每个学生的到达时间，请编程确定该课程是否被取消。如果该门课程被取消，则输出“Yes”，否则输出“No”。

假设教授在时刻0开始上课。

①如果一个学生的到达时间是非正整数，则表示该学生在上课前进入教室。

②如果一个学生的到达时间是正整数，则表示该学生在上课后进入教室。

③如果一个学生在时刻0进入教室，也被认为是在上课前进入教室。

假设到达时间的绝对值不超过100，学生数N不超过1000。要求在输入学生的到达时间之前，先输入N和K。

#### 已知函数原型：

//函数功能：根据数组a中记录的学生到达时间确定课程是否被取消，取消则返回1，否则返回0

int IsCancel(int a[], int n, int k);

### 输入

包括两行数据：

第1行是n,k的值。<br>
第2行是学生的到达时间。
### 输出

课程被取消，输出"YES"<br>
课程不取消，输出"NO"

### 我交的作业
```c
#include <stdio.h>

int IsCancel(int a[], int n, int k)
{
    int person = 0;
    for (int i = 0; i < n; i++)
    {
        if (a[i] < 0)
        {
            person++;
        }
    }
    // if (person < k)
    // {
    //     return 1;
    // }
    // return 0;
    return (person < k) ? 1 : 0;
}

int main()
{
    int n, k;
    scanf("%d %d", &n, &k);

    int count = 0;
    int arr[1000];

    while (scanf("%d", &arr[count]) == 1)
    {
       count++;
       if (count >= n)
       {
            break;
       }
    }
    if (IsCancel(arr, n, k))
    {
        printf("YES");
    }
    else
    {
        printf("NO");
    }

    return 0;
}
```
### 本次作业所做的改进
三元运算符
数组标准输入
