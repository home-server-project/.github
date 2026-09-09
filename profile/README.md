<p align="center">
  <img src="../logo/banner-navy-mid.png" alt="Home Server Project banner">
</p>

# Home Server Project

**Cloud-native technology, brought home.**

Home Server Project exists to make modern, cloud-native home-server technology practical for people who want a capable home lab without first having to become experts in Ignition, Butane, bootc internals, CoreOS partitioning, or container-host engineering.

The goal is simple: someone with solid everyday computer skills and a willingness to learn should be able to go from bare hardware to a modern immutable home server through a clear, understandable path.

Advanced concepts are not hidden. They are there when you want to learn them. They just should not be prerequisites for getting started.

## Why this project exists

Fedora CoreOS, Universal Blue uCore, AlmaLinux, bootc, Podman and systemd Quadlets are strong technologies, but the normal entry path can still be intimidating for a new home-lab user.

A person should not need to manually write Ignition or Butane, build custom installation media, understand image-based operating-system internals, or fight storage-layout details just to install a server and start learning.

Home Server Project focuses on that gap: a friendlier installation and management path around strong upstream foundations while keeping the underlying Linux, container and systemd model visible and understandable.

**Complexity should be available, not mandatory.**

## Choose your path

Home Server Project does not require users to choose a Home Server Project operating-system image. Upstream options remain first-class choices where the tooling supports them.

### Universal Blue uCore LTS

[Universal Blue uCore](https://github.com/ublue-os/ucore) provides practical server and HCI images built on Fedora CoreOS. It is also the upstream foundation used by Home Server Gina.

Home Server Installer can install upstream uCore directly, including **uCore Minimal LTS**, **uCore LTS** and **uCore HCI LTS**. Users who want the upstream experience without the Home Server Project additions can choose it directly.

Universal Blue and Fedora CoreOS provide the substantial operating-system, kernel, container, storage, virtualization and image-platform engineering underneath this path. Home Server Project does not replace that work.

### Home Server Gina

[Home Server Gina](https://github.com/home-server-project/home-server-gina) is a thin downstream layer built on Universal Blue uCore LTS.

Gina keeps the upstream Fedora CoreOS/uCore foundation and adds a deliberately small set of home-server administration, diagnostics, UPS and convenience tools. Gina and Gina HCI are available through Home Server Installer alongside the upstream uCore choices.

### Home Server Rose

[Home Server Rose](https://github.com/home-server-project/home-server-rose) uses a different foundation: AlmaLinux OS 10 and the Enterprise Linux ecosystem.

Rose follows the same Home Server Project philosophy but takes the more conservative path, with a slower-moving base and a broader built-in home-server tooling layer. AlmaLinux provides the core Enterprise Linux operating-system foundation; Home Server Project adds the Rose bootc image composition, home-server tooling, configuration and release pipeline.

Rose will use its own dedicated installation-media path through [Home Server Rose ISO](https://github.com/home-server-project/home-server-rose-iso). That repository exists but is not implemented yet.

Gina and Rose are not intended to compete as "better" and "worse" options. They provide two different upstream foundations for different preferences and use cases.

## Build. Install. Deploy.

### Build

[Home Server Gina Builder](https://github.com/home-server-project/home-server-gina-builder) is the normal user path for creating a personalized bootable Home Server Installer ISO in the user's own GitHub account.

The Builder embeds the user's **public SSH key** and builds the Installer media. It does not embed one operating-system image into the ISO.

### Install

[Home Server Installer](https://github.com/home-server-project/home-server-installer) is the interactive installation engine for the Gina/uCore path.

The current Installer presents five signed LTS choices:

- Home Server Gina LTS
- Home Server Gina HCI LTS
- uCore Minimal LTS
- uCore LTS
- uCore HCI LTS

The selected image is downloaded during installation. The Installer handles target-disk selection, storage layout, user setup, SSH configuration, image verification and direct installation so the user does not need to prepare Ignition or manually assemble a CoreOS installation path.

Rose will follow a separate dedicated ISO path rather than being added to the Gina/uCore Installer menu.

### Deploy

[Home Server Deployer](https://github.com/home-server-project/home-server-deployer) is in early Alpha development.

Its goal is an optional, friendly management layer for native Podman Quadlets without replacing Podman, systemd or the administrator's Quadlet files. Native Quadlets remain the source of truth, and deployed applications should continue running normally even if Deployer itself is stopped or removed.

## Projects

- [Home Server Gina](https://github.com/home-server-project/home-server-gina) — Fedora CoreOS + Universal Blue uCore LTS foundation with a thin Home Server Project layer.
- [Home Server Rose](https://github.com/home-server-project/home-server-rose) — AlmaLinux OS 10 / Enterprise Linux foundation with a broader Home Server Project server layer.
- [Home Server Gina Builder](https://github.com/home-server-project/home-server-gina-builder) — GitHub template for creating a personalized Home Server Installer ISO.
- [Home Server Installer](https://github.com/home-server-project/home-server-installer) — interactive direct installer for Gina and selected upstream uCore LTS images.
- [Home Server Rose ISO](https://github.com/home-server-project/home-server-rose-iso) — dedicated Rose installation-media project; repository created, implementation still to come.
- [Home Server Deployer](https://github.com/home-server-project/home-server-deployer) — early Alpha manager for native Podman Quadlets.

## Designed for home labs

Home Server Project is built around a few practical principles:

- make installation approachable on real hardware;
- use immutable, image-based operating-system foundations;
- keep applications in containers when they belong in containers;
- use Podman and native systemd Quadlets rather than inventing a second container model;
- provide sensible defaults without hiding important decisions;
- make virtualization available where useful without requiring everything to run inside VMs;
- stay close to upstream projects instead of unnecessarily replacing their work;
- write documentation for people learning the architecture, not only people who already know it.

The goal is not to remove Linux from the experience. It is to remove unnecessary barriers between a new home-lab user and a good Linux server foundation.

## What this project is not

Home Server Project is not:

- a replacement for Fedora CoreOS, Universal Blue uCore or AlmaLinux;
- another traditional Linux distribution built from scratch;
- an all-in-one NAS appliance;
- a platform that requires multiple virtual machines just to run containers;
- an attempt to hide the underlying Linux, Podman, systemd or Quadlet architecture.

## Upstream foundations and references

<details>
<summary><strong>Project and upstream links</strong></summary>

### Fedora CoreOS / Universal Blue path

- [Fedora CoreOS](https://fedoraproject.org/coreos/)
- [Universal Blue uCore](https://github.com/ublue-os/ucore)
- [Home Server Gina](https://github.com/home-server-project/home-server-gina)
- [Home Server Gina Builder](https://github.com/home-server-project/home-server-gina-builder)
- [Home Server Installer](https://github.com/home-server-project/home-server-installer)
- [Project Bluefin Knuckle](https://github.com/projectbluefin/knuckle) — upstream foundation for Home Server Installer

### AlmaLinux / Enterprise Linux path

- [AlmaLinux OS](https://almalinux.org/)
- [AlmaLinux bootc-images](https://github.com/AlmaLinux/bootc-images)
- [Home Server Rose](https://github.com/home-server-project/home-server-rose)
- [Home Server Rose ISO](https://github.com/home-server-project/home-server-rose-iso)

### Container and image platform

- [bootc](https://github.com/bootc-dev/bootc)
- [Podman](https://podman.io/)
- [systemd](https://systemd.io/)
- [Podman Quadlets](https://docs.podman.io/en/latest/markdown/podman-systemd.unit.5.html)

### Home Server Project

- [Home Server Project organization](https://github.com/home-server-project)
- [Home Server Deployer](https://github.com/home-server-project/home-server-deployer)

</details>

## Project philosophy

Build on strong upstream projects.

Keep the host understandable.

Put applications in containers when they belong there.

Make installation and deployment approachable.

Let people learn the deeper architecture when they are ready.

**Cloud-native technology, brought home.**
