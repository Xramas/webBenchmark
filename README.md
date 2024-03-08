# webBenchmark
基准测试工具会耗尽您的服务器带宽。

用户在使用本工具前请先查看授权及免责声明，webBenchmark仅仅是一个用于测试网页服务器性能的工具，用作其他用途，后果自负。

- random User-Agent on every Request
- customizable Referer Url,
- customizable header,
- concurrent routines as you wish, depends on you server performance.
- http post mode
- specify multi target ip, or resolved by system dns.
- randomly X-Forwarded-For and X-Real-IP (default on).

# Usage
    webBenchmark -c [COUNT] -s [URL] -r [REFERER]
    -c int
          concurrent routines for download (default 16)
    -r string
          referer url
    -s string
          target url (default "https://baidu.com")
    -i string
          custom ip address for that domain, multiple addresses automatically will be assigned randomly
    -H http header pattern
          http header pattern, use Random with number prefix will generate random string, same key will be overwritten
    -f string
          randomized X-Forwarded-For and X-Real-IP address
    -p string
          post content

# Linux
    chmod +x webBenchmark_linux_x64
    ./webBenchmark_linux_x64 -c 128 -s https://www.xramas.com

## Advanced example
    # send request to 10.0.0.1 and 10.0.0.2 for https://target.url with 32 concurrent threads 
    # and refer is https://refer.url 
    ./webBenchmark_linux_x64 -c 32 -s https://target.url -r https://refer.url -i 10.0.0.1 -i 10.0.0.2
    # send request to https://target.url with header regid:123 and sign:Random10
    ./webBenchmark_linux_x64 -s https://target.url -H 'regid:123' -H 'sign:QpXDYHdVzB'
    
