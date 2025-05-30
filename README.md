# Advanced Programming - Module 11

## Hello Minikube
> Compare the application logs before and after you exposed it as a Service. Try to open the app several times while the proxy into the Service is running. What do you see in the logs? Does the number of logs increase each time you open the app?

Foto di bawah ini merupakan kondisi logs sebelum saya mengexpose aplikasi sebagai suatu service.
<img width="554" alt="Screenshot 2025-05-30 at 14 14 01" src="https://github.com/user-attachments/assets/0014418b-bf18-4beb-af51-42b090bfad2b" />

Foto di bawah ini merupakan kondisi logs setelah saya mengexpose aplikasi sebagai service. Terdapat 2 baris logs baru, yaitu logs GET/ yang menandakan saya berhasil mengunjungi aplikasi tersebut dengan GET request.
<img width="548" alt="Screenshot 2025-05-30 at 14 14 21" src="https://github.com/user-attachments/assets/d4b23028-5115-496f-bed2-784d8c247a94" />

Foto di bawah ini merupakan log setelah saya mengakses aplikasinya kembali. Dapat dilihat bahwa logs bertambah lagi sebanyak 2 baris yang isinya sama seperti logs sebelumnya dan hanya berbeda di bagian waktu akses.
<img width="562" alt="Screenshot 2025-05-30 at 14 16 09" src="https://github.com/user-attachments/assets/71855a47-225f-4cd0-9502-64351c4626fa" />

> Notice that there are two versions of kubectl get invocation during this tutorial section. The first does not have any option, while the latter has -n option with value set to kube-system. What is the purpose of the -n option and why did the output not list the pods/services that you explicitly created?

Opsi `-n` pada perintah `kubectl get` digunakan untuk menentukan namespace tempat Kubernetes mencari resource seperti pod atau service. Secara default, Kubernetes akan mencari resource di namespace default. Sementara itu, jika kita menuliskan `-n kube-system`, maka yang ditampilkan hanyalah resource yang berada di namespace `kube-system` yaitu namespace khusus yang digunakan oleh komponen internal Kubernetes.
