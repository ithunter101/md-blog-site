This is a very simple blog built with Django, Django REST Framework, React/Redux, and Bootstrap, deployed with Docker, and served with nginx-uwsgi. It can be useful as an example of integrating Django with React, as a starter project, or as a beautiful and simple blogging tool =)

I have built this project by following [these](https://www.udemy.com/react-redux/)  [two](https://www.udemy.com/react-redux-tutorial/) awesome React courses, I highly recommend them to anybody who wants to learn React! [This](https://teamtreehouse.com/library/django-rest-framework)  Django REST Framework course really helped me to build the backend, and [this](https://www.udemy.com/docker-tutorial-for-devops-run-docker-containers/) course was incredibly helpful for learning Docker.

<!-- 
You can check out the demo [here](). You can [login]() with username "admin" and password "1234" to try creating and editing posts(please be nice, don't post anything that might offend anybody).
 -->

![Screenshot](https://raw.githubusercontent.com/ithunter101/md-blog-site/master/assets/blog-screenshot-2.png)

![Screenshot](https://raw.githubusercontent.com/ithunter101/md-blog-site/master/assets/blog-screenshot-5.png)


## Installation

Installing and running this blog is very simple. Clone this repo, and then simply run:

	docker-compose up
	(use -d flag to run it in the background)

After that, the blog will be running on the localhost. Isn't Docker amazing? =)

You will also need to attach to the container by running this:

	docker exec -i -t backend  /bin/bash

run migrations:

	python3.5 manage.py migrate

and create an admin user with:

	python3.5 manage.py createsuperuser

Now you can go to localhost/login url, login and begin blogging!

Important: Before running it on the server, go to backend/config/env, and change "SECRET_KEY" and "POSTGRES\_PASSWORD" to something unique.

To deploy it online, go to Digital Ocean, create a Docker droplet, and repeat the same commands. Then you will need to go to the networking tab, and create two A records pointing to the droplet:

	yourawesomeblog.com
	api.yourawesomeblog.com

Like so:

![Screenshot](https://raw.githubusercontent.com/ithunter101/md-blog-site/master/assets/dns-records.png)


You can also go to:

    api.yourawesomeblog.com/admin

to access the admin panel. You can add categories there, if you want to better organize your posts, and you can create a settings object where you can add an about page and fill in the meta info(site title, keywords, etc).

# Clean up
- Pass all the speed tests.  
  https://developers.google.com/speed/pagespeed/insights/  
  https://tools.pingdom.com/  
  https://gtmetrix.com/  
- Pass all mobile tests  
  https://search.google.com/search-console/mobile-friendly
- Pass all SEO tests  
  https://seositecheckup.com
- Write tests
- Migrate automatically. entrypoint.sh?



