# Introduction #

Welcome, this is rpmwand project.

`rpmwand' helps your rpm building work. In most cases, rpm spec file is too complicated to build an rpm package which contains only a few files. But with rpmwand, you can make a sample rpm by just two steps, and with the sample package, your whole rpm building work can be easily set up.

# Details #

## Who needs this program ##

  * Shell script maintainers.
  * Rpm builder who just has a few script files and wish to make them to be shipped in rpm package.
  * Rpm builder who doesn't require any compile steps in building the package.
  * Virtual package builder for rpm dependencies which are used to set up a new machine.

## How to use ##

Let's assume you are building named "ganghee" package.

### Step 1 ###
```
rpmwand init ganghee
```

In this step, package environments are prepared for ganghee rpm. you can check
  * ganghee.spec.in
  * ganghee-skel
  * ganghee-files.txt

### Step 2 ###

```
rpmwand build ganghee 1.0.0 1
```

You can build ganghee-1.0.0-1.noarch.rpm with above command. Isn't it simple?

### Step 3 ###

Place your own files into ganghee-skel directory which is faked root directory.

```
rpmwand files ganghee
```

And this command updates ganghee-files.txt from ganghee-skel directory. and again,

```
rpmwand build ganghee 1.0.0 2
```

Now, you can get ganghee-1.0.0-2.noarch.rpm file.

TODO: more detailed description.