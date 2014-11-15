.. link: 
.. description: An open source communication and collaboration tool. Currenty, web IRC as a service
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
          <h1 class="waartaa-banner">
            waartaa &nbsp;<strong class="waartaaversion">0.2</strong> is here!
          </h1>
      </div>
      <div class="row">
        <img class="waartaa-banner-img img-rounded" src="/assets/images/waartaa_com_splash.svg">
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
                <script data-gittip-username="rtnpro"
                        data-gittip-widget="button"
                                src="//gttp.co/v1.js"></script>
              </li>
              <li>
                <a href="https://twitter.com/share" class="twitter-share-button" data-url="https://www.waartaa.com/" data-lang="en" data-text="Waartaa - an open source communication and collaboration tool">Tweet</a>
              </li>
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
        <h2 class="lead" style="font-size: 40px; padding: 5px; color: #938D9E; text-align: center;">
          An Open Source communication and collaboration tool
        </h2>
        <h1>
          <div class="row" style="color: #938D9E;">
            <div class="col-md-2 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="glyphicon glyphicon-cloud"></icon>
              <p style="font-size: 18px;">Central logging</p>
            </div>
            <div class="col-md-2 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="glyphicon glyphicon-time"></icon>
              <p style="font-size: 18px;">24x7 IRC</p>
            </div>
            <div class="col-md-2 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="glyphicon glyphicon-user"></icon>
              <p style="font-size: 18px;">Unique identity</p>
            </div>
            <div class="col-md-2 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="glyphicon glyphicon-envelope"></icon>
              <p style="font-size: 18px;">Notifications</p>
            </div>
            <div class="col-md-2 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="fa fa-globe"></icon>
              <p style="font-size: 18px;">Global access</p>
            </div>
            <div class="col-md-2 col-sm-6 col-xs-6" style="text-align: center;">
              <icon class="fa fa-tablet"></icon>
              <icon class="fa fa-desktop"></icon>
              <icon class="fa fa-mobile"></icon>
              <p style="font-size: 18px;">Responsive</p>
            </div>
          </div>
        </h1>
      </div>
      <!-- Features at a glance end -->


.. raw:: html

    <h2>Quickstart</h2>
    <hr/>


.. container:: row no-container

    .. container:: col-md-6 no-container

        .. container:: panel panel-info no-container

            .. container:: panel-heading no-container

                Development

            .. container:: panel-body no-container

                .. code-block:: bash

                    curl https://install.meteor.com/ | sh
                    git clone https://github.com/waartaa/waartaa.git
                    cd waartaa
                    npm install collections
                    cd app
                    cp server/settings-local.js-dist server/settings-local.js
                    meteor

    .. container:: col-md-6 no-container

        .. container:: panel panel-info no-container

            .. container:: panel-heading no-container

                Deployment

            .. container:: panel-body no-container

                1. Setup development environment as mentioned above.
                2. Install ansible
                    - Fedora/CentOS/RHEL: ``sudo yum install ansible``
                    - Ubuntu/Debian: ``sudo apt-get install ansible``
                    - Python pip: ``sudo pip install ansible``
                3. Copy provisions/hosts.sample file to, let’s say, provisions/hosts and customize it as needed.
                4. Configure SSH access and firewall in your servers as needed.
                5. Setup servers, build and deploy waartaa: ``ansible -i provisions/hosts provisions/deploy.yml``


.. container:: row no-container

    .. raw:: html

        <h2>Contribute</h2>
        <hr/>


    - Start using our `demo <https://try.waartaa.com>`_ instance or setup your own instance
    - Report bugs, feature requests and feedback in general at
      `https://github.com/waartaa/waartaa/issues
      <https://github.com/waartaa/waartaa/issues>`_
    - You can start working on issues marked as ``EasyFix`` `here
      <https://github.com/waartaa/waartaa/issues>`_. If you need help,
      just comment on the issue, and we'll get back.
    - You can also ping us on IRC at ``#waartaa`` on ``Freenode``.

