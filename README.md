adnlib
==========

Simple Go implementation of app.net API.

Installing
----------

Best way to isntall this package is by running goinstall:

    go get github.com/robteix/adnlib

And then you can import it in your code like this:

    import (
            ...
            "github.com/robteix/adnlib"
            ...
        )

General use
-----------

1. First create a `adnlib.Transport` that will handle OAuth:

        config := &Config{
                    ConsumerKey: "your-consumer-key",
                    ConsumerSecret: "your-consumer-secret",
                    Callback: "http://www.my-app.com/my-callback"}
        token := &Token{
                    OAuthSecret: "your-oauth-secret",
                    OAuthToken: "your-oauth-token"}
        tr := &adnlib.Transport{Config: config,
                              Token: token}

2. Create a `adnlib` object:

        tl := adnlib.New(tr.Client())

3. Post something:

        tl.Stream.Post("this is cool!").Do()



TODO: document how to perform the oauth authentication.

License
-------

Copyright 2011 The Tweetlib Authors.  All rights reserved.

Redistribution and use in source and binary forms, with or without
modification, are permitted provided that the following conditions are
met:

   * Redistributions of source code must retain the above copyright
notice, this list of conditions and the following disclaimer.
   * Redistributions in binary form must reproduce the above
copyright notice, this list of conditions and the following disclaimer
in the documentation and/or other materials provided with the
distribution.
   * Neither the name of Google Inc. nor the names of its
contributors may be used to endorse or promote products derived from
this software without specific prior written permission.

THIS SOFTWARE IS PROVIDED BY THE COPYRIGHT HOLDERS AND CONTRIBUTORS
"AS IS" AND ANY EXPRESS OR IMPLIED WARRANTIES, INCLUDING, BUT NOT
LIMITED TO, THE IMPLIED WARRANTIES OF MERCHANTABILITY AND FITNESS FOR
A PARTICULAR PURPOSE ARE DISCLAIMED. IN NO EVENT SHALL THE COPYRIGHT
OWNER OR CONTRIBUTORS BE LIABLE FOR ANY DIRECT, INDIRECT, INCIDENTAL,
SPECIAL, EXEMPLARY, OR CONSEQUENTIAL DAMAGES (INCLUDING, BUT NOT
LIMITED TO, PROCUREMENT OF SUBSTITUTE GOODS OR SERVICES; LOSS OF USE,
DATA, OR PROFITS; OR BUSINESS INTERRUPTION) HOWEVER CAUSED AND ON ANY
THEORY OF LIABILITY, WHETHER IN CONTRACT, STRICT LIABILITY, OR TORT
(INCLUDING NEGLIGENCE OR OTHERWISE) ARISING IN ANY WAY OUT OF THE USE
OF THIS SOFTWARE, EVEN IF ADVISED OF THE POSSIBILITY OF SUCH DAMAGE.
