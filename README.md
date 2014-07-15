# acl -- one advanced C/C++ lib for UNIX and WINDOWS

## ����
acl ������һ����ƽ̨��֧��LINUX��WIN32��Solaris��MacOS��FreeBSD��������ͨ�ſ⼰��������̿�ܣ�ͬʱ�ṩ�����ʵ�ù��ܿ⡣ͨ���ÿ⣬�û����Էǳ����׵ر�д֧�ֶ���ģʽ(���̡߳�����̡�����������������UDP��ʽ)�ķ���������WEB Ӧ�ó������ݿ�Ӧ�ó��򡣴��⣬�ÿ⻹�ṩ�˳���Ӧ�õĿͻ���ͨ�ſ⣨�磺HTTP��SMTP��ICMP��memcache��beanstalk����������ʽ�����⣺XML/JSON/MIME/BASE64/UUCODE/QPCODE/RFC2047 etc��

��������Ҫ���� 5 ���⼰����ʾ����5 �����˵�����£�
-    1) lib_acl: �ÿ���������Ŀ⣬���� 4 ����������ڸÿ�; �ÿ��� C ����ʵ�֡�
-    2) lib_protocol: �ÿ���Ҫʵ���� http Э�鼰 icmp/ping Э��; �ÿ��� C ����ʵ�֡�
-    3) lib_acl_cpp: �ÿ��� C++ ���Է�װ�� lib_acl/lib_protocol �����⣬ͬʱ������һЩ�����м�ֵ�Ĺ���Ӧ�á�
-    4) lib_dict: �ÿ���Ҫʵ���� KEY-VALUE ���ֵ�ʽ�洢�⣬�ÿ����⻹������ BDB, CDB �Լ� tokyocabinet �⡣
-    5) lib_tls: �ÿ��װ�� openssl �⣬ʹ lib_acl ��ͨ��ģʽ����֧�� ssl��

## ƽ̨֧�ּ�����
��������Ŀǰ֧�� Linux(AS4,5,6, CS4,5,6), Windows, MacOS, FreeBSD, Solaris��
* Linux/UNIX: ������Ϊ gcc��ֱ�����ն������з�ʽ�·ֱ���� lib_acl/lib_protocol/lib_acl_cpp/lib_dict/lib_tls Ŀ¼�£����� make ����ɡ�
* Windows: ������ VC2003/VC2008/VC2010/VC2012 ���б��롣(�����Ҫ�� VC6/VC2005 ���룬���Բο� VC2003 �ı�������)��

���� WIN32 ������ʹ�ö�̬��ʱ�м�����Ҫע�⣺
* ʹ�� lib_acl �Ķ�̬��ʱ����Ҫ���û��Ĺ���Ԥ����: ACL_DLL;
* ʹ�� lib_protocol ��̬���е� HTTP ��� ICMP ��ʱ����Ҫ�ڹ�����Ԥ���� HTTP_DLL �� ICMP_DLL;
* ʹ�� lib_acl_cpp �Ķ�̬��ʱ����Ҫ�ڹ�����Ԥ���� ACL_CPP_DLL�������ʹ���� VC2003 ���뻷������ҪԤ���� VC2003;
* ʹ�� lib_dict �Ķ�̬��ʱ����Ҫ�ڹ�����Ԥ���� DICT_DLL;
* ʹ�� lib_tls �Ķ�̬��ʱ����Ҫ�ڹ�����Ԥ���� TLS_DLL��

## Ŀ¼�ṹ˵��

### lib_acl
-    1 init : ��Ҫ���ڳ�ʼ�� acl ������
-    2 stdlib : ��һЩ�Ƚϻ����Ĺ��ܺ����⣬�� stdlib/ ��Ŀ¼����Ҫ����һЩ�й���־��¼������/�ļ�������VSTRING��������ȹ��ܺ������� stdlib/ �»��ж���Ŀ¼�����£�
-    2.1 common : ��Ŀ¼��ҪΪһЩ���õ����ݽṹ���㷨�Ĺ��ܺ����⣬���ϣ���������С���̬���顢��ջ�����桢ƽ���������ģʽƥ�����ȣ�
-    2.2 memory : ��Ŀ¼��Ҫ�������ڴ������صĺ����⣬���ڴ����������У�顢�ڴ�ع����ڴ���Ƭ����ȣ�
-    2.3 filedir : ��Ŀ¼��Ҫ������Ŀ¼������Ŀ¼��������صĿ⣻
-    2.4 configure : ��Ŀ¼��Ҫ���������ļ��ķ����⣻
-    2.5 iostuff : ��Ŀ¼��Ҫ����һЩ���õ�IO�����ĺ����⣬���/д��ʱ������IO���������ģʽ�ȣ�
-    2.6 string : ��Ŀ¼��Ҫ����һЩ���õ��ַ��������Ŀ⣬�ṩ�˱ȱ�׼C������Ч���ַ����������ܣ�
-    2.7 debug : ��Ҫ����Э�������ڴ��й¶�ȹ��ܣ�
-    2.8 sys : ��Ҫ���벻ͬ����ϵͳƽ̨��ص�API�ķ�װ�����⣻
-    **3 net: �������������صĺ����⣬��������������������ӡ�DNS��ѯ���׽ӿڲ������õȹ��ܣ�**
-    3.1 connect : ��Ҫ��������������صĺ����⣬�����������ӡ����׽ӿ����ӵȣ�
-    3.2 listen : ��Ҫ�������������صĺ����⣬����������������׽ӿڼ����ȣ�
-    3.3 dns : ��Ҫ����DNS������ѯ��صĺ����⣬������ gethostbyname �Ƚӿڵķ�װ����RFC1035��׼ֱ�ӷ���UDP����ʽ���в�ѯ�ȹ��ܣ�
-    **4 event : ��Ҫ��װ�� select/poll/epoll/iocp/win message/kqueue/devpoll ��ϵͳAPI�ӿڣ�ʹ���������¼���������Ч���򵥣����⻹������ʱ���ӿڣ�acl �еĺܶ�����Ӧ�ö����õ���Щ�ӿڣ��� aio��master ��ģ�飻**
-    **5 aio : ��Ҫ���������첽�����Ĺ��ܺ��������׺������ڴ���߲���ʱ�зǳ��ߵ�Ч�ʣ������ṩ�˱Ȼ���API��Ϊ�߼��ĵ��÷�ʽ����ʹ���� libevent ֮��ĺ������Ϊ�򵥣��������̰߳�ȫ�ģ�**
-    6 msg : ��Ҫ�����˻����̵߳���Ϣ�¼��������������Ϣ�¼����ܣ�
-    7 thread : ��Ҫ�Ƿ�װ�˸���OSƽ̨�µĻ����߳�API��ʹ����ӿڱ���һ���ԣ�������ƽ̨�Ĳ����ԣ�ͬʱ���ṩ�˰�פ���̳߳صĺ����⣬�Լ������ֲ߳̾���������չ��
-    8 db : ��Ҫ��һЩ�����ݿ��йصĹ��ܿ⣬������һ��ͨ�õ����ݿ����ӳصĿ�ܣ�����ʵ����mysql�����ӳ�ʵ������һ���򵥵��ڴ����ݿ⣨�ɹ�ϣ������ƽ���������϶��ɣ���ZDB���ݴ洢���棬����һ����Ч�Ļ������ּ��Ĵ洢���棻
-    9 proctl : win32 ƽ̨�¸��ӽ��̿��ƹ��ܿ⣻
-    10 code : �������뺯���⣬���� base64����롢URL������Լ�һЩ�����ַ�������ȣ�
-    11 unit_test : �����йؽ��� C ���Ե�Ԫ���ԵĹ��ܿ⣻
-    12 xml: ��һ����ʽ�� xml ��������������������֧������������ʽ����ͨ�ţ�
-    13 json: ��һ����ʽ�� json ��������������������֧������������ʽ����ͨ�ţ�
-    **14 master: ���� UNIX ������֧�ֶ��ַ�����ģʽ�ķ�������ܣ�Ŀǰ��Ҫ֧�ֶ����ģʽ������̶��߳�ģʽ������̷�����ģʽ������̴�����ģʽ�� UDP ͨ��ģʽ��**

### lib_protocol
-    1 http: HTTP Э����صĿ⣬֧�� HTTP/1.1��ͨѶ��ʽ֧��ͬ��/�첽��ʽ
-    2 icmp: icmp/ping Э��⣬֧��ͬ��/�첽ͨ�ŷ�ʽ
-    3 smtp: �ʼ��ͻ��˷���Э���

### lib_acl_cpp
-    1 stdlib: ��Ҫ�����ַ���������(string)��xml/json �����⣬zlib ѹ����(������ zlib ��), ��־��¼��, �ַ���ת��(��UNIX��������Ҫ iconv ��), memcached �ͻ���, ������(֧���߳������ļ���);
-    **2 stream: ֧��������/�ļ�����֧������/����������ͨ�ŷ�ʽ���ڷ�����ģʽ��֧�� select/poll/epoll/iocp/win32 message/kqueue/devpoll��֧�� ssl ���ܴ���(��������������ʽ����Ҫ polarssl��);**
-    3 ipc: �ڷ�����ͨ�ŷ�ʽ���ṩ������ģ���������ģ�����ϵķ�ʽ;
-    **4 http: �Ƚ������� HTTP ͨ�ſ⼰Э������⣬֧�ֿͻ��˼������ģʽ��֧�� ssl/gzip ���䷽ʽ; ֧�������� Java HttpServlet ��ʽ�Ĵ󲿷ֽӿڣ������д CGI �� WEB ����������**
-    5 db: ��װ�� MYSQL/SQLITE �⣬֧�����ݿ����ӳأ�
-    6 hsocket: ʵ���������� handler-socket �ͻ���ͨ�ſ⣻
-    **7 mime: ֧�����������ʼ�������صĿ�(�ʼ��� rfc2045-rfc2047/rfc822/base64/uucode ���뼰�����).**
-    **8 master: ��װ�� C ��ķ�������ܿ�**
-    9 beanstalk: ��Ϣ����Ӧ�� beanstalkd �Ŀͻ���ͨ�ſ�
-    10 connpool: ͨ�õ����ӳؿ�
-    11 hscoket: mysql ��� handle-socket �Ŀͻ���ͨ�ſ�
-    12 memcache: memcached Ӧ�õĿͻ��˿�
-    13 queue: �����ļ����в�����
-    14 ipc: ����/������ͨ�����Ͽ�
-    15 session: HTTP �Ự��

### ʾ��
- acl ��Ŀ�д����Ĳ��Լ�Ӧ��ʾ������Ҫ������ʾ���������£�
#### acl/samples����Ŀ¼�µ�������Ҫ�ǻ��� lib_acl �� lib_protocol �����������
-    1.1 acl: ��ӡ��ǰ acl ��汾�ų���
-    1.2 aio/client: ������ io �ͻ���
-    1.3 aio/server: ������ io ������
-    1.4 base64: base64 ��/�������
-    1.5 btree: ����������
-    1.6 cache: ���󻺴����
-    1.7 cache2: ���󻺴����
-    1.8 cgi_env: CGI ����������� CGI ��������
-    1.9 chunk_chain: ���ֿ����ݳ���
-    1.10 configure: �����ļ��������
-    1.11 connect: ����ͻ������ӳ���
-    1.12 dbpool: ���ݿ����ӳس���
-    1.13 dlink: ���ֿ�����㷨����
-    1.14 dns: ������ѯ����
-    1.15 dns_req: ������ѯ����
-    1.16 event: �¼��������
-    1.17 fifo: �Ƚ��ȳ��㷨����
-    1.18 file: �ļ����������
-    1.19 file_fmt: �� UNIX �µ� \n תΪ WIN32 �µ� \r\n ���߷���ת������
-    1.20 FileDir: win32 ��Ŀ¼��������
-    1.21 flock: �ļ����������
-    1.22 gc: �ڴ��Զ����ճ���
-    1.23 htable: ��ϣ�������
-    1.24 http/header: http �ͻ��˳���
-    1.25 http/url_get1: ��ҳ���ؿͻ��˳���
-    1.26 http/url_get2: ��ҳ���ؿͻ��˳���
-    1.27 http/url_get3: ��ҳ���ؿͻ��˳���
-    1.28 http_aio: �򵥵� HTTP �첽���س���
-    1.29 http_client: WIN32 �� HTTP �ͻ��˳���
-    1.30 http_probe: HTTP �ͻ��˳���
-    1.31 ifconf: ��ȡ���������ĳ���
-    1.32 iplink: IP ��ַ�ι������
-    1.33 iterator: C ��ʽ���б����ĳ���
-    1.34 json: json ���������
-    1.35 json2: json ���������
-    1.36 json3: json ���������
-    1.37 jt2ft: ����ת�������
-    1.38 log: ��־�������
-    1.39 master/aio_echo: ���������Է���������
-    1.40 master/aio_proxy: ������ TCP �������
-    1.41 master/ioctl_echo2: ���̻߳���ʾ����������
-    1.42 master/ioctl_echo3: ���̻߳���ʾ����������
-    1.43 master/master_notify: ���̷߳���������
-    1.44 master/master_threads: ���̷߳���������
-    1.45 master/single_echo: ����̻���ʾ����������
-    1.46 master/trigger: ����������������
-    1.47 master/udp_echo: UDP ���Է���������
-    1.48 memdb: �򵥵��ڴ����ݿ����
-    1.49 mempool: �ڴ�س���
-    1.50 mkdir: �����༶Ŀ¼����
-    1.51 net: ���������
-    1.52 ping: ����/������ PING ����
-    1.53 pipe: �ܵ��������
-    1.54 proctl: WIN32 �¸��ӽ��̳���
-    1.55 resolve: ������������
-    1.56 server: �򵥵ķ���������
-    1.57 server1: �򵥵ķ���������
-    1.58 slice: �ڴ����Ƭ����
-    1.59 slice_mem: �ڴ����Ƭ����
-    1.60 smtp_client: smtp �ͻ��˷��ų���
-    1.61 string: acl �ַ����������
-    1.62 thread: �̳߳���
-    1.63 token_tree: 256 ��������
-    1.64 udp_clinet: UDP �ͻ��˳���
-    1.65 udp_server: UDP ����������
-    1.66 urlcode: URL ���봦�����
-    1.67 vstream: IO �������������
-    1.68 vstream_client: ����ͻ���������
-    1.69 vstream_fseek: �ļ����������
-    1.70 vstream_fseek2: �ļ����������
-    1.71 vstream_popen: �ܵ����������
-    1.71 vstream_popen2: �ܵ����������
-    1.71 vstream_popen3: �ܵ����������
-    1.72 vstream_server: �������˳���
-    1.73 xml: XML ��������
-    1.74 xml2: XML ��������
-    1.75 zdb: ����KEY/VALUE �ļ��洢�������

#### acl/lib_acl_cpp/samples����Ŀ¼�µ����ӻ����ǻ��� lib_acl_cpp ��д�� C++ ����
-    2.1 aio/aio_client: ����������ͻ��˳���
-    2.2 aio/aio_dns: ���������������ͻ��˳���
-    2.3 aio/aio_echo: ���������Է���������
-    2.4 aio/aio_ipc: ����/���������ϵ��������
-    2.5 aio/aio_server: ����������������
-    2.6 beanstalk: ����Ӧ�� beanstalkd �Ŀͻ��˳���
-    2.7 benchmark: �����ܲ�����صĳ���
-    2.8 cgi: �򵥵� WEB CGI ����
-    2.9 cgi_upload: �����ϴ��ļ��� CGI ����
-    2.10 charset: �ַ���ת������
-    2.11 check_trigger: ���Զ�� HTTP ������״̬�Ĵ���������
-    2.12 connect_manager: �ͻ������ӳؼ�Ⱥ�������
-    2.13 db_service: �����ݿ���صĳ���
-    2.14 dbpool: ʹ�����ݿ�ͻ������ӳصĳ���
-    2.15 dircopy: Ŀ¼�ļ���������
-    2.16 final_class: ��ֹ�̳������
-    2.17 flock: �ļ����������
-    2.18 fs_benchmark: �ļ�ϵͳѹ�����Գ���
-    2.19 fstream: �ļ�������
-    2.20 gui_rpc: WIN32 ������������ WIN32 �������Ϣ���ϵ�����
-    2.21 hsclient: handle-socket �ͻ��˳���
-    2.22 http_client: HTTP �ͻ��˳���
-    2.23 http_client2: HTTP �ͻ��˳���
-    2.24 http_mime: HTTP Э��� MIME ��ʽ�������
-    2.25 http_request: ʹ�� http_request ��� HTTP �ͻ��˳���
-    2.26 http_request_manager: HTTP �ͻ������ӳؼ�Ⱥ����
-    2.27 http_request_pool: HTTP �ͻ������ӳس���
-    2.28 http_request2: ʹ�� http_request ��� HTTP �ͻ��˳���
-    2.29 http_response: ʹ�� http_reponse ����Ӧ HTTP �ͻ�������ĳ���
-    2.30 http_server: �򵥵� HTTP ����������
-    2.31 http_servlet: ������ JAVA HttpServlet �ĳ���
-    2.32 http_servlet2: ������ JAVA HttpServlet �ĳ���
-    2.33 HttpClient: �򵥵� HTTP �ͻ��˳���
-    2.34 json: json �ַ��������������
-    2.35 logger: ��־����
-    2.36 master_aio: ����������������
-    2.37 master_aio_proxy: ������ TCP �������������
-    2.38 master_http_aio: �򵥵ķ����� HTTP ����������
-    2.39 master_http_rpc: ����/���������ϵ� HTTP ����������
-    2.40 master_http_threads: ���߳� HTTP ����������
-    2.40 master_http_threads2: ���߳� HTTP ����������
-    2.41 maser_proc: ���̳ط���������
-    2.42 master_threads: ���̷߳���������
-    2.43 master_trigger: ����������������
-    2.44 master_udp: UDP ͨ�ŷ���������
-    2.45 master_udp_threads: ���߳� UDP ͨ�ŷ���������
-    2.46 md5: md5 �������
-    2.47 mem_cache: memcached �ͻ��˳���
-    2.47 memcache_pool: memcached ֧�����ӳصĿͻ��˳���
-    2.48 mime: �ʼ� MIME �����������
-    2.49 mime_base64: MIME BASE64 ��ʽ�������
-    2.50 mime_qp: MIME QP ��ʽ�������
-    2.51 mime_xxcode: MIME XXCODE ��ʽ�������
-    2.52 mysql: mysql �ͻ��˳���
-    2.53 mysql2: mysql �ͻ��˳���
-    2.54 rfc822: �ʼ��� RFC822 Э�鴦�����
-    2.55 rfc2047: �ʼ��� RFC2047 Э�鴦�����
-    2.56 rpc_download: ��������/���������Ϸ�ʽ���� HTTP ���صĳ���
-    2.57 scan_dir: Ŀ¼�ݹ�ɨ�����
-    2.58 singleton: ��������
-    2.59 session: �Ự����
-    2.60 socket_client: ����ͻ��˳���
-    2.61 socket_stream: �������������
-    2.62 sqlite: sqlite ���ݿ����
-    2.63 ssl_aio_client: SSL ����������ͻ��˳���
-    2.64 ssl_clinet: SSL ��������ͻ��˳���
-    2.65 string: ��̬�������������
-    2.66 string2: ��̬�������������
-    2.67 thread: ���̳߳���
-    2.68 thread_client: ���߳̿ͻ��˳���
-    2.69 thread_pool: �̳߳س���
-    2.70 udp_client: UDP ͨ�ſͻ��˳���
-    2.71 url_coder: URL �ࡢ�������
-    2.72 win_dbservice: ���� WIN32 ͼ�ν�������ݿ⴦�����
-    2.73 winaio: ���� WIN32 ͼ�ν���ķ������ͻ��˳���
-    2.74 xml: XML ��������������
-    2.75 zlib: ѹ����ʽ�������

#### acl/app����Ŀ¼�µ�������Ҫ��һЩ�Ƚ�ʵ�õ�����
-    **3.1 wizard: �������ɻ��� acl ��������ܵĳ���ģ��ĳ���**
-    3.2 gid: ��������ȫ��Ψһ ID �ŵķ�����򣨺��ͻ��˿⣩
-    3.3 net_tools: ������������״̬�ĳ���
-    3.4 master_dispatch: �Ժ�˷��������� TCP ���ӵ����Ӿ������
-    3.5 jaws��Ŀǰ�����ã������� acl �ķ�����ͨ��ģ��� HTTP ģ��д��һ�����׵� HTTP �߲�������������

## ����
- WEB վ��: http://www.iteye.com
- Download: https://sourceforge.net/projects/acl
- QQ Ⱥ: 242722074
