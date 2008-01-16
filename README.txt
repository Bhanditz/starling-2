= Name

Starling - a light weight server for reliable distributed message passing.

= Synopsis

  # Start the Starling server as a daemonized process:
  starling -h 192.168.1.1 -d

  # Put messages onto a queue:
  require 'memcache'
  starling = MemCache.new('192.168.1.1:22122')
  starling.set('my_queue', 12345)

  # Get messages from the queue:
  require 'memcache'
  starling = MemCache.new('192.168.1.1:22122')
  loop { puts starling.get('my_queue') }

  # See the Starling documentation for more information.

= Description

Starling is a powerful but simple messaging server that enables reliable 
distributed queuing with an absolutely minimal overhead. It speaks the
MemCache protocol for maximum cross-platform compatibility. Any language
that speaks MemCache can take advantage of Starling's queue facilities.

= Known Issues

* Starling is "slow" as far as messaging systems are concerned. In practice,
  it's fast enough. If you'd like to help make it faster please do. Starting
  points would be to use an event-driven interface, and get rid of threading.

= Authors

Blaine Cook <romeda@gmail.com>

= Copyright

Starling - a light-weight server for reliable distributed message passing.
Copyright 2007 Blaine Cook <blaine@twitter.com>, Twitter Inc.
