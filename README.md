# AMWA NMOS Device Configuration Specification

[![Lint Status](https://github.com/AMWA-TV/is-14/workflows/Lint/badge.svg)](https://github.com/AMWA-TV/is-14/actions?query=workflow%3ALint)
[![Render Status](https://github.com/AMWA-TV/is-14/workflows/Render/badge.svg)](https://github.com/AMWA-TV/is-14/actions?query=workflow%3ARender)

This repository holds the source for this Specification, part of the family of [Networked Media Open Specifications](https://specs.amwa.tv/nmos) from the [Advanced Media Workflow Association](https://amwa.tv)

<!-- INTRO-START -->

### What does it do?

Enables the configuration of an NMOS Nodes' [MS-05-02](https://specs.amwa.tv/ms-05-02/) model using a backup and restore API.

### Why does it matter?

Defines a standard way of backing up and restoring [MS-05-02](https://specs.amwa.tv/ms-05-02/) models, as well as defining a way to manage dynamically configurable [MS-05-02](https://specs.amwa.tv/ms-05-02/) models.

### How does it work?

- It specifies an HTTP API for backing up an NMOS Nodes' [MS-05-02](https://specs.amwa.tv/ms-05-02/) model as a JSON backup dataset.
- The API can be used to restore that backup dataset to the NMOS Node.
- The API can be used to change the structure of 'rebuildable' parts of the [MS-05-02](https://specs.amwa.tv/ms-05-02/) model dynamically, if the NMOS Node allows.

<!-- INTRO-END -->

## Getting started

An open source media node framework is available in the form of [nmos-cpp](https://github.com/sony/nmos-cpp).  
An example mock application is available in the form of the [NMOS Device Control Mock Application](https://github.com/AMWA-TV/nmos-device-control-mock).  
A testing tool is available in the form of the [NMOS API Testing Tool](https://github.com/AMWA-TV/nmos-testing).



