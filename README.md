# DLP Endpoint Policy Lab

Practical cybersecurity lab focused on Data Loss Prevention (DLP) policies for removable storage control in a simulated Windows endpoint environment.

> Note: The full project report is currently available in Spanish.

## Overview

This project documents the design and implementation of a DLP strategy to restrict the use of removable storage devices and reduce the risk of data exfiltration, malware introduction and uncontrolled handling of sensitive information.

The lab was developed in a Windows 10 Pro virtual environment using VirtualBox, Group Policy configuration and Microsoft Management Console (MMC). The objective was to apply the Principle of Least Privilege by blocking USB access for standard users while maintaining controlled exceptions for authorised administrator profiles.

## Key areas covered

- Data Loss Prevention strategy
- Data classification and access control
- Principle of Least Privilege
- Removable storage restrictions
- Windows Group Policy configuration
- MMC-based granular policy exceptions
- Endpoint security validation
- Security awareness and monitoring considerations

## Technical implementation

The lab includes:

- Configuration of a Windows 10 Pro virtual machine in VirtualBox
- USB controller and device filtering setup
- Global removable storage restriction using Local Group Policy
- Read and write access denial for removable disks
- Validation with a non-privileged user account
- Granular exception configuration through MMC
- Final verification showing administrator access allowed and standard user access blocked

## Report

The repository includes the project report:

**DLP-Security-Policy-Project.pdf**

The report covers DLP concepts, data classification, role-based access control, monitoring, prevention of data leaks, user awareness and the technical validation of removable storage restrictions.

## Tools and technologies

- Windows 10 Pro
- VirtualBox
- Local Group Policy Editor
- Microsoft Management Console
- USB device filtering
- Endpoint access control
- Data Loss Prevention concepts

## Repository structure

- DLP-Security-Policy-Project.pdf — Full DLP policy and technical implementation report
- README.md — Project overview and repository documentation

## Status

Completed practical lab project.

## Disclaimer

This project was developed in a controlled educational environment. It is intended to demonstrate endpoint security policy implementation, least-privilege access control and DLP-related technical documentation.
