.. link: 
.. description: 
.. tags: 
.. date: 2014/02/10 01:55:26
.. slug: index
.. title: Waartaa
.. template: home.tmpl


.. raw:: html

  <div id="waartaa-intro" class="col-md-12">
    <div>
      <!-- Banner -->
      <div class="waartaa-banner-main-content row">
        <div class="col-md-5">
          <h1 class="waartaa-banner">
            Waartaa &nbsp;<small class="waartaaversion">0.1</small>
          </h1>
          <h1 class="waartaa-subbanner">
            <span class="waartaa-mission-logo-irc">IRC</span> + 
            <icon class="waartaa-mission-logo-cloud glyphicon glyphicon-cloud"></icon> =
            <icon class="waartaa-mission-logo-love glyphicon glyphicon-heart"></icon>
          </h1>
          <p style="text-align: center;">
            An open source communication tool built with love.
          </p>
        </div>
        <div class="waartaa-banner-img-container col-md-7">
          <img class="waartaa-banner-img img-rounded" src="/assets/images/waartaa.png">
        </div>
      </div>
      <!-- Bannder end -->

      <!-- Social buttons -->
      <div id="social-btns">
        <div class="container">
          <ul class="list-inline">
            <li>
              <iframe src="https://www.waartaa.com/github-btn.html?user=waartaa&repo=waartaa&type=watch&count=true" allowtransparency="true" frameborder="0" scrolling="0" width="110" height="20"></iframe>
            </li>
            <li>
              <iframe src="https://www.waartaa.com/github-btn.html?user=waartaa&repo=waartaa&type=fork&count=true" allowtransparency="true" frameborder="0" scrolling="0" width="95" height="20"></iframe>
            </li>
            <li>
                <a href="https://twitter.com/share" class="twitter-share-button" data-url="http://www.waartaa.com/" data-lang="en">Tweet</a>
            <li>
              <iframe id="twitter-widget-1" scrolling="no" frameborder="0" allowtransparency="true" src="https://platform.twitter.com/widgets/follow_button.1390956745.html#_=1391800265777&amp;id=twitter-widget-1&amp;lang=en&amp;screen_name=waartaa&amp;show_count=true&amp;show_screen_name=true&amp;size=m" class="twitter-follow-button twitter-follow-button" title="Twitter Follow Button" data-twttr-rendered="true" style="width: 236px; height: 20px;"></iframe>
            </li>
          </ul>
        </div>
      </div>
      <!-- Social buttons end -->

      <!-- Banner large button -->
      <p style="text-align: center; margin-top: 20px;">
        <a id="waartaa-try-btn" class="btn btn-primary btn-lg" role="button" href="https://try.waartaa.com/">
          Give it a go!
        </a>
      </p>
      <!-- Banner large button end -->
    </div>

    <!-- Features at a glance -->
    <div style="margin-top: 40px;">
      <div class="row" style="margin-bottom: 40px;">
        <h1 class="lead" style="font-size: 64px; padding: 5px; color: #938D9E; text-align: center;">
          IRC client as a service
        </h1>
        <h1>
          <div class="row" style="color: #938D9E;">
            <div class="col-md-3 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="glyphicon glyphicon-cloud"></icon>
              <p style="font-size: 18px;">Central logging</p>
            </div>
            <div class="col-md-3 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="glyphicon glyphicon-time"></icon>
              <p style="font-size: 18px;">24x7 online</p>
            </div>
            <div class="col-md-3 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="glyphicon glyphicon-user"></icon>
              <p style="font-size: 18px;">Unique identity</p>
            </div>
            <div class="col-md-3 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="glyphicon glyphicon-envelope"></icon>
              <p style="font-size: 18px;">Notifications</p>
            </div>
          </div>
        </h1>
      </div>
      <!-- Features at a glance end -->

      <!-- Quickstart -->
      <div class="row">
        <div class="col-md-6" style="color: #938D9E;">
          <h1 style="text-align: center; margin-top: 25%; margin-bottom: 25%;">
            <icon class="glyphicon glyphicon-wrench" style="font-size: 64px; top: 12px;"></icon>
              Easy setup
          </h1>
        </div>
        <div class="col-md-6">
          <div class="panel panel-info">
            <div class="panel-heading">
              Quickstart
            </div>
            <div class="panel-body" style="overflow: auto;">
              <ol>
              <li>Install system dependencies: <code>node</code>, <code>npm</code> for your system. For example:

                <ol>
                  <li>For Fedora, you can do: <code>$ sudo yum install nodejs npm -y</code>
                  </li>
                  <li>For Mac OS X, you can install them via brew: <code>$ brew install node npm</code>
                  </li>
                  <li>For Debian/Ubuntu install only node.js and it will include npm as: 
                     <code>$ sudo add-apt-repository ppa:chris-lea/node.js<br>
                       $ sudo apt-get update<br>
                       $ sudo apt-get install nodejs
                     </code>
                  </li>
                  <li>Else, you can always compile from source.</li>
                </ol>
              </li>
              <li>Get the source: <code>$ git clone --recursive https://github.com/waartaa/waartaa.git</code>
              </li>
              <li>Go to <strong>waartaa</strong>'s repository directory just cloned: <code>$ cd waartaa</code>
              </li>
              <li>Run setup script: <code>$ ./setup.sh</code>
              </li>
              <li>Customize <code>waartaa/server/settings-local.js</code> as needed.</li>
              <li>Go to waartaa meteor project's directory: <code>$ cd waartaa</code>
              </li>
              <li>Run waartaa: <code>$ meteor</code>
              </li>
              </ol>
            </div>
          </div>
        </div>
      </div>
      <!-- Quickstart end -->
    </div>
  </div>

