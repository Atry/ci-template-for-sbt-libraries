# CI template for Sbt libraries

This is a template for easy setup CI

## Usage

### Step 1:

Create a secret [gist](https://gist.github.com/) or other private GIT repository and put the following file into it:

#### `id_rsa`

Your RSA private key used to push changes to Github

#### `secring.asc`

Your PGP private key used to sign your artifacts that will be pushed to Nexus

#### `sonatype.sbt`
A Sbt configuration file that contains your username and password for Nexus.
  
``` sbt
credentials += Credentials("Sonatype Nexus Repository Manager", "oss.sonatype.org", "your-username", "your-password")
```

#### `haxelib.sbt`

A Sbt configuration file that contains your username and password for Haxelib.
  
``` sbt
haxelibSubmitUsername := "your-username"

haxelibSubmitPassword := "your-password"
```

### Step 2:

``` bash
git pull https://github.com/Atry/ci-template-for-sbt-libraries.git ci
```

or 

``` bash
git pull https://github.com/Atry/ci-template-for-sbt-libraries.git haxe
```

### Step 3:

Merge conflicts.

### Step 4:

Rename `deploy.sh.disable` to `deploy.sh`
