# Page 18
### 随机数和时间

**随机数生成**

```cpp
#include <cstdlib>
#include <ctime>

// 设置随机种子
srand(time(0));            // 以当前时间作为种子，程序运行一次设置一次

// 生成随机数
int x = rand();            // 生成 0 ~ RAND_MAX 之间的随机整数
int y = rand() % 100;      // 生成 0 ~ 99 之间的随机整数
int z = rand() % 100 + 1;  // 生成 1 ~ 100 之间的随机整数
```

**C++11 更好的随机数方式**

```cpp
#include <random>

random_device rd;
mt19937 gen(rd());                         // 随机引擎
uniform_int_distribution<> dis(1, 100);    // 1 ~ 100 均匀分布

int x = dis(gen);  // 生成随机数
```

**时间函数**

| 函数 | 说明 |
| :--- | :--- |
| `time(0)` 或 `time(NULL)` | 返回当前时间戳（自 1970-01-01 起的秒数） |
| `clock()` | 返回程序运行至今的 CPU 时钟数 |

```cpp
#include <ctime>

time_t now = time(0);                // 当前时间戳
cout << now << endl;

// 计时
clock_t start = clock();
// ... 执行代码 ...
clock_t end = clock();
cout << "耗时: " << (double)(end - start) / CLOCKS_PER_SEC << "秒" << endl;
```