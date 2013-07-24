CHANGELOG.md
----
* This is a fork of https://github.com/perplexes/mctop which supports
  the binary mcached protocol.

* Updated (downgraded?) to work with Ruby 1.8.7 - 1.8.7 doesn't support
  force_encoding and strings are already binary. Probably won't work with
  1.9.x anymore.

* Changed the sniffer to look at the data portion of the packets
  instead of the TCP headers so that we don't randomly hit \x80|\x81
  in the header data.

* Since we are only looking at the TCP data portion, I anchored the
  search for \x80|\81 to the start of the packet, so that we don't
  match in the middle of the data.
