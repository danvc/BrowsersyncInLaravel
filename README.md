# BrowsersyncInLaravel
It's a short guide about how to setup browsersync in **Laravel** inside **Docker**

1. Install all needed to get the BrowserSync working with gulp and Laravel. You can get all details here: [Browser-sync](https://laravel.com/docs/5.3/elixir#browser-sync)

2. Setup your proxy according the IP address of your docker container:
```
elixir(function(mix) {
    mix.browserSync({
        proxy: 'https://192.168.99.100',
        notify: false
    });
});
```
Run in terminal: `gulp watch`

It will show you details about the host and the port. Note the **port** number.
[![browser5.png](https://s24.postimg.org/bjupm15yd/browser5.png)](https://postimg.org/image/808rw838h/)

3. Open ``Kitematic`` (that was with Docker) and follow the instructions below:

 * Select the container that you want to get Browsersync working.

![browser1.png](https://s27.postimg.org/g2178fv7n/browser1.png)

* Click in the **Settings** button, on panel on right side.
![browser2.png](https://s23.postimg.org/4hj3btepl/browser2.png)

* Click in the **Port** panel according the image below:
![browser3.png](https://s27.postimg.org/hjmnjzzyb/browser3.png)

* The last settings is just ADD the port (that you got when running ``gulp watch`` to the red rectangles, according the image)
[![browser4.png](https://s28.postimg.org/wdynmfjql/browser4.png)](https://postimg.org/image/ol7zugdrd/)

The last step is simple click on the **Save** button access your website trough the docker-ip:port/url
```
http://192.168.99.100:3000/
```
**OBS**: Replace the 192.168.99.100 IP by your Docker IP
