# tutorial11

1. Compare the application logs before and after you exposed it as a Service.
   Try to open the app several times while the proxy into the Service is running.
   What do you see in the logs? Does the number of logs increase each time you open the app?

Ya, saya melihat detail HTTP request setiap saya membuka aplikasi baru. Hal ini menunjukkan bahwa setelah 
service diexpose, maka log aplikasi bertambah karena menunjukkan detail dari seluruh aplikasi yang terbuka tersebut. 

2. Notice that there are two versions of `kubectl get` invocation during this tutorial section.
   The first does not have any option, while the latter has `-n` option with value set to
   `kube-system`.
   What is the purpose of the `-n` option and why did the output not list the pods/services that you
   explicitly created?
    kubectl get adalah command yang dipakai untuk fetch semua node di cluster dan detail yang bersangkutan. Opsi -n adalah
    opsi namespace yang digunakan untuk mengisolasi resource di dalam satu cluster. Maka dari itu, perintah kubectl get yang
    menggunakan opsi ini hanya akan mengambil pod dan services dengan namespace tertentu, sebagai contoh kubectl get pods,services -n kube-system
    hanya akan mengambil pods dan services yang memiliki namespace kube-system.