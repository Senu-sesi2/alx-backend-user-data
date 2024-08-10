# 0x02. Session authentication

## Resources
* <https://intranet.alxswe.com/rltoken/oofk0VhuS0ZFZTNTVrQeaQ>
* <https://intranet.alxswe.com/rltoken/peLV8xuJ4PDJMOVFqk-d2g>
* <https://intranet.alxswe.com/rltoken/AI1tFR5XriGfR8Tz7YTYQA>
* <https://intranet.alxswe.com/rltoken/QYfI5oW6OHUmHDzwKV1Qsw>

## Learning Objectives
* What authentication means
* What session authentication means
* What Cookies are
* How to send Cookies
* How to parse Cookies

## Sample Task
Copy all your work of the 0x06. Basic authentication project in this new folder.

In this version, you implemented a Basic authentication for giving you access to all User endpoints:

* `GET /api/v1/users`
* `POST /api/v1/users`
* `GET /api/v1/users/<user_id>`
* `PUT /api/v1/users/<user_id>`
* `DELETE /api/v1/users/<user_id>`
Add a new endpoint: `GET /users/me` to retrieve the authenticated `User` object.

* Copy folders `models` and api from the previous project `0x06. Basic authentication`
* Update `@app.before_request` in `api/v1/app.py`:
* Assign the result of `auth.current_user(request)` to `request.current_user`
* Update method for the route `GET /api/v1/users/<user_id>` in `api/v1/views/users.py`:
	* If `<user_id>` is equal to `me` and `request.current_user` is `None: abort(404)`
	* If `<user_id>` is equal to `me` and `request.current_user` is not `None`: return the authenticated `User` in a JSON response (like a normal case of `GET /api/v1/users/<user_id>` where `<user_id>` is a valid `User` ID)
Otherwise, keep the same behavior
