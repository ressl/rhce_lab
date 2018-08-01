# RHCE Lab

This lab is for learning for the Red Hat RHCSA (ex200) and Red Hat RHCE (ex300) exams.

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

For the lab you should install the following software:

* [Git](https://git-scm.com/downloads)
* [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
* [Vagrant](https://www.vagrantup.com/downloads.html)

### Installing

The first step is to clone the project and jump into:

```
git clone git@github.com:safematix/rhce_lab.git
```

## Starting the lab

Start the lab with the following commands:

```
cd rhce_lab
vagrant up
```

Jump into the vm's:

```
vagrant ssh server1
vagrant ssh tester1
vagrant ssh outsider1
```

## Stopping the lab

Stop the lab with the following commands:

```
vagrant destroy --force
```

## Built With

* [Vagrant](https://www.vagrantup.com) - HashiCorp, Inc.
* [VirtualBox](https://www.virtualbox.org) - Oracle

## Contributing

Please read [CONTRIBUTING](CONTRIBUTING.md) for details on our code of conduct, and the process for submitting pull requests to us.

## Versioning

We use [SemVer](http://semver.org/) for versioning. For the versions available, see the [tags on this repository](https://github.com/safematix/rhce_lab/tags). 

## Authors

* **Robert Ressl** - *Initial work* - [Robert Ressl](https://github.com/safematix)

See also the list of [contributors](https://github.com/safematix/rhce_lab/contributors) who participated in this project.

## License

This project is licensed under the GNU Affero General Public License v3.0 License - see the [LICENSE](LICENSE) file for details

## Acknowledgments

## Thanks to…

