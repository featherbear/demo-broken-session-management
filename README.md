# Broken Session Management Demo

Don't _just_ clear your local session, also invalidate it from the server! Otherwise someone with knowledge of the session token can reuse it..

***How else should we manage sessions?***  
Don't store them in plain-text, just like passwords!  
When sessions are stored, they need to be hashed as well - otherwise a compromised database will contain (hundreds of) valid sessions!

Also, sessions should have expiries!

---

## Running

* Install Node.js + Yarn
* Install dependencies `yarn install`
* Run with `yarn dev`

---

## Demo Instructions (Client-side only)

* Log in with either `admin:admin` or `user:user`
* Memorise the session token
  * Click [Reveal Session Token]
* Perform a bad logout (by means of clearing the token from the browser)
  * Click [Log Out (Bad)]
* Attempt to log back in
  * Click [Set Session Token]
  * Enter session token
* Success

## Demo Instructions (Server-side invalidation)

* Log in with either `admin:admin` or `user:user`
* Memorise the session token
  * Click [Reveal Session Token]
* Perform a good logout (by means of invalidating the token on the server)
  * Click [Log Out (Good)]
* Attempt to log back in
  * Click [Set Session Token]
  * Enter session token
* Failure
