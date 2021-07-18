<h3 align="center">Hidden parameters discovery suite wrapper</h3>

#

<p align="center"><img src="https://user-images.githubusercontent.com/87244850/126019752-09dc8b3c-c6a4-49f3-9398-7974cbae3d03.png" width="50%"/></p>



The tool helps to find hidden parameters that can be vulnerable or can reveal interesting functionality that other hunters miss. Greater accuracy is achieved thanks to the line-by-line comparison of pages, comparison of response code and reflections.

## Features

- Selecting multiple requests from the Proxy or Repeater tab.
- Each selected request is executed in a separate thread.
- Automatic Issue creation when hidden parameter is found.
- HTTP/2 Support.
- Requests with detected parameters are visible in the Proxy tab.
- Issue is added with severity `Information` when WAF is detected.
- Automatic detection of injection point. If the request body exists, then parameters in URL-Query are ignored.
- Custom injectin point can be defined using `%s` or `&%s`
<p align="center"><img src="https://user-images.githubusercontent.com/87244850/125835832-a24d2cec-4dc1-4ffd-afff-12f4e99c409c.png" width="79%"/></p>

## Usage
- There are four search choices available: 
    - Small Wordlist (Recommended, `25000` words, 5 threads)
    - Large Wordlist (`63000` words, 15 threads)
    - x8083 - all request will be proxied via port 8083 (for example, you can configure the port in Burp)
    - Debug Params - the minimum number of requests to detect only debug parameters and parameters based on response

<p align="center">&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;&#160;<img src="https://user-images.githubusercontent.com/87244850/125835974-5679ec1a-0126-48a2-82ba-1861c94ed551.png" width="83%"/></p>


## Test
Feel free to check whether the tool works as expected and compare it with other tools at https://4rt.one/. There are 2 reflected parameters, 4 parameters that change code/headers/body, and one extra parameter with a not random value.

## Detected parameters
<p align="center"><img src="https://user-images.githubusercontent.com/87244850/125836031-681af553-c3ef-4314-a431-dd34e49fdb86.png" width="87%"/></p>

## Acknowledgement
Thanks to [Sh1Yo](https://github.com/Sh1Yo) for the wonderful x8 utility. He added special functions into it so that we could write this wrapper. We also spotted some bugs, specifically in HTTP/2, for Burp Suite compatibility. To examine and understand the project in detail, or if you need a command line version, click [here](https://github.com/Sh1Yo/x8).

## Installation
- Linux
    - from releases
        ```bash
        Burp -> Extender -> ./x8-Burp/src/linux_x8.py
        ```
- Windows
    - from releases
        ```bash
        Burp -> Extender -> ./x8-Burp/src/win_x8.py
        ```
