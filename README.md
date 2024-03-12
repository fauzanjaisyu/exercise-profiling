# **Modul 5**
## JMeter Report and Test Results
### **Endpoint** `/all-student`
Test Result JMeter
<img src="src/image/testresult1.png" alt="all-student">
Before Optimization JMeter:
<img src="src/image/before-refactor1.png" alt="all-student"/>
After Optimization JMeter:
<img src="src/image/after-refactor1.png" alt="all-student"/>

Execution Time `getAllStudentWithCourses()` from Intellij Profiler:

| Before | After | Diff Percentage |
| -- | -- | -- |
| 16,589 ms | 1,498 ms | 90.97% |

### **Endpoint** `/all-student-name`
Test Result JMeter:
<img src="src/image/testresult2.png" alt="all-student-name">
Before Optimization JMeter:
<img src="src/image/before-refactor2.png" alt="all-student-name"/>
After Optimization JMeter:
<img src="src/image/after-refactor2.png" alt="all-student-name"/>

Execution Time `joinStudentNames()` from Intellij Profiler:

| Before | After  | Diff Percentage |
|--------|--------| -- |
| 22,197 ms | 1,167 ms | 94.74% |

### **Endpoint** `/highest-gpa`
Test Result JMeter:
<img src="src/image/testresult3.png" alt="all-student-name">
Before Optimization JMeter:
<img src="src/image/before-refactor3.png" alt="all-student-name"/>
After Optimization JMeter:
<img src="src/image/after-refactor3.png" alt="all-student-name"/>

Execution Time `findStudentWithHighestGpa()` from Intellij Profiler:

| Before | After | Diff Percentage |
|--------|-------| -- |
| 919 ms | 144 ms | 84.33% |
