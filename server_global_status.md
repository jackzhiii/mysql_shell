# 获取服务器状态的请求数， 线程连接数， 线程正在运行的数目

mysqladmin -uroot -proot@888111 ext -i1 | awk ' \
/Queries/{q=$4-qp;qp=$4} \
/Threads_connected/{tc=$4} \
/Threads_running/{printf "%5d %5d %5d\n", q, tc, $4}'

mysqladmin: [Warning] Using a password on the command line interface can be insecure.
  554     3     1
    1     3     1
    1     3     1
    1     3     1
    1     3     1
    1     3     1
    1     3     1
    1     3     1