Heroku buildpack: Mono
======================

Consider this a work in-progress / hack.

Building via Vulcan
-------------------
1) Download mono tarball and extract into buildpack-mono/mono-2.10.2
http://www.mono-project.com/Compiling_Mono_From_Tarball

2) Issue vulcan build
vulcan build -s ./mono-2.10.2 -p /tmp/mono210 -c "./autogen.sh --enable-nls=no --prefix=/tmp/mono210 && ./configure --enable-nls=no --prefix=/tmp/mono210 && make install"

3) In theory at this point you should have tar compatible for Heroku. Sadly, I have yet to reach this stage.
Current status: 
#<Net::HTTPServiceUnavailable 503 Service Unavailable readbody=true>
!! Unknown error, no build output given



Usage
-----
    $ heroku create --stack cedar --buildpack http://github.com/BenHall/heroku-buildpack-mono