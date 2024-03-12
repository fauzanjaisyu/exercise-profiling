# **Modul 5**
## Difference between the approach of performance testing with JMeter and profiling with IntelliJ Profiler in the context of optimizing application performance

Setidaknya ada 3 poin perbedaan optimisasi aplikasi menggunakan JMeter dengan IntelliJ Profiler:
1. Fokus: JMeter berfokus pada simulasi interaksi pengguna dan pengujian beban, sedang IntelliJ Profiler berfokus pada analisis performa kode, penggunaan memori, dan
   aktivitas thread
2. Testing Environment: JMeter biasanya digunakan untuk mensimulasikan berbagai skenario pengguna, sedangkan profiler biasanya digunakan dalam lingkungan pengembangan
3. Use Cases: JMeter cocok untuk menilai kinerja dan skalabilitas sistem secara keseluruhan, sementara profiler sangat penting untuk mengidentifikasi
   hambatan kinerja tingkat kode tertentu dan masalah terkait memori.

## How does the profiling process help you in identifying and understanding the weak points in your application?

Profiling membantu saya untuk mengetahui bagian/method mana pada kode saya yang tidak optimal atau memakan memory dan waktu paling besar, sehingga saya bisa melakukan
refactor pada method tersebut
 
## Do you think IntelliJ Profiler is effective in assisting you to analyze and identify bottlenecks in your application code?

Ya, IntelliJ Profiler memberikan ragam metode untuk menampilkan hambatan pada kode, seperti flame graph, method list, dan timeline. Metode - metode ini membantu saya
untuk mengidentifikasi hambatan yang ada

## Challenges

Karena data yang diberikan oleh profiler sangat rinci dan kompleks, hal ini menyukitkan saya untuk memahami hasil yang diberikan dengan benar dan mengidentifikasi kode bagian
mana yang harus benar-benar dilakukan perbaikan, selain itu proses refactoring dari bottleneck yang ada juga merupakan tantangan bagi saya

## Main benefits from using IntelliJ Profiler

Manfaat yang saya dapatkan dari menggunakan profiler ini adalah saya dapat mengetahui bottleneck dari suatu kode pada Intellij itu sendiri secara langsung, sehingga bottlneck
tadi dapat diperbaiki sesegera mungkin

## How do you handle situations where the results from profiling with IntelliJ Profiler are not entirely consistent with findings from performance testing using JMeter?

Selama mengerjakan modul 5 ini, saya tidak menemukan hasil JMeter yang inkonsisten dengan IntelliJ Profiler, namun apabila terjadi ketidaksesuaian, saya akan memastikan   
verifikasi konfigurasi dan skenario pengujian sudah sesuai lalu mengulangi pengujian. Namun apabila masih terkendala, saya akan googling sana googling sini, atau kalau
masih terkendala juga saya akan bertanya kepada orang yang kompeten seperti kakak asdos maupun teman saya.

## Strategies

Strategi yang saya lakukan adalah dengan mengurangi iterasi sebagaimana pada method `joinStudentNames()` dan method `getAllStudentsWithCourses()` serta menggunakan
`@Query(value = "SELECT * FROM students ORDER BY gpa DESC LIMIT 1", nativeQuery = true)` pada `StudentRepository` untuk mengoptimalkan method `findStudentWithHighestGpa()`

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
