CrowdMapper
===========

Real-time collaborative application for tagging streams of geospatial data, built on top of the Meteor Javascript platform. Built with the humanitarian goal of crisis mapping in mind.

[![CrowdMapper Replay](http://share.gifyoutube.com/mLnMWR.gif)](https://www.youtube.com/watch?v=xJYq_kh6NlI)

This project uses [TurkServer](https://github.com/HarvardEconCS/turkserver-meteor) to study how people can organize to do crisis mapping.

## Dependencies

This project has several dependencies that can't be installed by Meteor.

The data analysis uses [libzmq](https://github.com/zeromq/libzmq) for Node.js to make RPC calls to algorithms implemented in Python, as outlined in [this blog post](http://ianhinsdale.com/code/2013/12/08/communicating-between-nodejs-and-python/). If you don't have ZeroMQ installed on your system, you will see an error when starting the Meteor app (it should still start) and you won't be able to start the Python computation process or run any of the data analysis methods.
       
To make the analysis algorithms available, first install the `libzmq` and `libevent` libraries, using whatever is appropriate for your system. For example, on Ubuntu:
       
```
apt-get install libzmq-dev
apt-get install libevent
```

If all the above works, Meteor should be able to install the `zerorpc` npm package as part of the app without any issues.

In addition, install the python dependencies for ZeroRPC, and Munkres (the Hungarian algorithm):
       
```
pip install pyzmq
pip install zerorpc
pip install munkres
```       
