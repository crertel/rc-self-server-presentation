
# Setting Up Your Own Server II
## Chris Ertel 2019-06-03

---

## What we'll cover today

* Checking on VPS
* Setting up DNS records
* Setting up user accounts
* Setting up Nginx

---

# Checking on VPS

--

## Connecting to your prgmr instance OOB console

* What is an OOB consoole?
* The **out of band** console
* It's always there for you, even if you screw up SSH.
* Or firewall rules.
* Or keys.

--

## Connecting to your prgmr instance OOB console

```bash
$ ssh -i <your keyfile> <hostname>@<hostanem>.console.xen.prgmr.com
```

--

## Connecting to your prgmr instance OOB console

That should give you a screen that looks like:

![sample screen](./images/01_xen_console.png)

--

## Checking the external IP

You can use the system status page to get your external IPs

![sample status](./images/04_system_status.png)

---

# Setting up DNS records

Go to your domain registrar and setup two records:

* *A record* for `@` at the IP from earlier
* *A record* for `www` at the IP from earlier

---

# Setting up user accounts

You can't be root all the time! We need to:

* Create a normal user
* Add that user to sudoers
* Remove root password login

-- 

## Creating your own user

```bash
# adduser <username>
```

--

## Creating your own user

![sample user creation](./images/02_adding_a_user.png)

--

## Adding user to sudoers

```
$ usermod -aG sudo <username>
```

--

## Test that the user can sudo!

**VERY IMPORTANT.**

--

## Remove root login password

```bash
$ sudo passwd -dl root
```

---

# Setting up DNS records

---

# Setting up Nginx

---