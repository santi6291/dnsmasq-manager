# dnsmasq-manager

Simple dnsmasq wrapper for managing host resolvers

## Getting Started 
Clone repo

```
git clone git@github.com:santi6291/dnsmasq-manager
```

Run Make: make it cli command 

```
make
```

## Usage 

### Help

```
$ dnsmasq-manager

Usage:	 dnsmasq-manager [COMMAND] [arg...]

Commands
	 install 	 [HOSTNAME]	 To install inital hostname require
	 uninstall 		         Uninstall dnsmasq and related directories/files
	 add 	         [HOSTNAME]	 Add new hostname
	 rm 	         [HOSTNAME]	 Remove hostname
```

### Install

```
$ dnsmasq-manager install [HOSTNAME]
```

- Give it a hostname for inistal setup
- Installs `dnsmasq`
- Creates `/etc/resolver/` directory
- Append hostname to `/usr/local/etc/dnsmasq.conf`
- Initate on machine boot - copies: `homebrew.mxcl.dnsmasq.plist` -> `/Library/LaunchDaemons`
- Create resolver file `/etc/resolver/[HOSTNAME]`

### Uninstall

```
$ dnsmasq-manager uninstall
```

- removes everythign that was installed above :)

### add

```
$ dnsmasq-manager add [HOSTNAME]
```

- adds new hostname
- Append hostname to `/usr/local/etc/dnsmasq.conf`
- Create resolver file `/etc/resolver/[HOSTNAME]`

### rm

```
$ dnsmasq-manager rm [HOSTNAME]
```

- remove hostname
- removes hostname from `/usr/local/etc/dnsmasq.conf`
- removes resolver file `/etc/resolver/[HOSTNAME]`
