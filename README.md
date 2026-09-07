# Home Server Project

**Cloud-native technology, brought home.**

Home Server Project exists to make cloud-native home-server technology easier to understand, install, and use on real hardware.

The goal is not to create another Linux distribution or an all-in-one home-server platform. Instead, the project builds on existing upstream technologies and adds a friendlier path for people who want the benefits of Fedora CoreOS, uCore, bootc, Podman, and Quadlets without first needing to become cloud-platform engineers.

## Upstream foundations

Home Server Project builds on:

- [Fedora CoreOS](https://github.com/coreos/fedora-coreos-tracker) — the immutable, automatically updating Fedora CoreOS platform.
- [Universal Blue uCore](https://github.com/ublue-os/ucore) — server-focused images built on Fedora CoreOS.

The underlying operating system, kernel, bootc stack, container stack, virtualization stack, storage stack, drivers, and core platform engineering remain upstream.

Home Server Project focuses on the home-server experience around those foundations.

## Build. Install. Deploy.

### Build

Create personalized installation media for your own server.

The planned Home Server Builder is designed as a reusable GitHub template rather than a central ISO factory. A user will be able to use the template from their own GitHub account, provide their own choices and public SSH key, and build personalized installation media for their own needs.

The same template can be reused later to build another ISO with a different image, SSH key, or supported configuration.

### Install

Turn the installation media into a working machine.

Home Server Installer is the installation engine. It is being developed to provide a safer and more understandable path for installing supported bootc-based server images on real hardware.

The project is intended to support Fedora CoreOS, uCore variants, Home Server uCore images, and compatible user-provided images as those paths are tested and validated.

### Deploy

Run and manage self-hosted services with Podman Quadlets.

Home Server Deployer is planned, but development has not started yet.

The goal is to provide a friendly way to generate and manage customizable Quadlets for common self-hosted applications without hiding the underlying container model from the user.

A future direction may also include assistance with translating Docker Compose configurations into Quadlets, but that is not part of the initial scope.

## Current projects

### Home Server uCore

A lightweight downstream uCore image with a small set of practical host-side administration tools for home servers.

Repository:
https://github.com/home-server-project/home-server-ucore

The project intentionally keeps the custom layer small. Applications that naturally belong in containers stay in containers.

### Home Server Installer

A friendly installation engine for bootc-based home servers.

Repository:
https://github.com/home-server-project/home-server-installer

The installer is currently alpha software and is being developed and tested around an explicit, safety-first installation flow.

## Planned projects

### Home Server Builder

Status: in development.

The Builder will be published as a GitHub template containing the workflows, configuration, and supporting logic needed for users to build their own personalized installation media in their own GitHub account.

### Home Server Deployer

Status: planned.

The Deployer will focus on creating and managing Podman Quadlets for common self-hosted services through a friendly, customizable workflow.

## What this project is not

Home Server Project is not:

- a fork of Fedora CoreOS;
- a fork of uCore;
- a new Linux distribution;
- a replacement for the upstream projects;
- an all-in-one NAS appliance;
- a virtualization-first platform that requires multiple VMs just to run containers.

The project is intended to make a modern, container-native home-server stack more accessible while keeping the underlying architecture understandable.

## Project philosophy

Use strong upstream foundations.

Keep the host operating system small.

Run applications as containers when they belong in containers.

Make installation and deployment understandable.

Do not hide important decisions from the user.

Provide a practical path from bare hardware to a useful home server.

**Cloud-native technology, brought home.**
