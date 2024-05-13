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

3. What is the difference between Rolling Update and Recreate deployment strategy?
Hint: Read the Deployments documentation.
Rolling Update meminimalisir versi lama, sehingga sedikit demi sedikit bisa digantikan oleh versi baru, serta memberikan opsi
bagi pengguna untuk rollback ke versi lama jika versi baru kurang memuaskan, sedangkan recreate deployment langsung mematikan
versi lama, dan membuat versi baru ketika veresi lama sudah dihentikan sebagai penggantinya.

4. Try deploying the Spring Petclinic REST using Recreate deployment strategy and document
   your attempt. Prepare different manifest files for executing Recreate deployment strategy.

5. What do you think are the benefits of using Kubernetes manifest files? Recall your experience
   in deploying the app manually and compare it to your experience when deploying the same app
   by applying the manifest files (i.e., invoking `kubectl apply -f` command) to the cluster.
<img src="Screenshot (482).png">
Menggunakan manifest file jauh lebih cepat dari deploy manual, cukup menggunakan apply -f dan aplikasi 
sudah terkonfigur secara langsung. Kelemahannya adalah ketika ada perubahan pada manifest file yang tidak sesuai dengan 
deployment aslinya maka mungkin bisa terjadi error.

