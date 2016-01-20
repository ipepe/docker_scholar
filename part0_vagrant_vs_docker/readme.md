# Vagrant vs Docker?
## Vagrant: Tworzy i konfiguruje lekkie, odtwarzalne i mobilne środowiska deweloperskie.
Vagrant jest narzędziem do odtwarzalnego tworzenia środowisk na maszynach wirtualnych z użyciem aplikacji Oracle's VirtualBox lub VMWare. Vagrant zajmuje się koordynacją poleceń instalujących oprogramowanie w sposób jakby prowadził każdy instalator po kolei za rączkę. Takie działanie jest określane jako "provisioning".

![Image](vm_vs_container.jpeg)

## Docker: Projekt otwartego oprogramowania do pakowania, wysyłania i uruchamiania aplikacji jako lekkie kontenery.
Działanie funkcji Dockera pokrywa się troche z funkcjami Vagranta (lub kto chce na odwrót). Docker pozwala określić process instalacji oprogramowania na systemie operacyjnym kontenera. Jednakże znacząco się różni w technologiach jakie do tego wykorzystuje. Docker używa "kontenerów Linuxowych", które nie są maszynami wirtualnymi per se, ale są wyizolowanymi procesami działającymi na wyizolowanym systemie plików. Docker też posiada narzędzie do koordynacji poleceń instalujących oprogramowanie w celu "provisioningu" kontenerów.

## Po angielsku(oryginalnie):
```
Vagrant: Create and configure lightweight, reproducible, and portable development environments.

It provides a reproducible way to generate fully virtualized machines using either Oracle's VirtualBox or VMWare technology as providers. Vagrant can coordinate with a configuration management software to continue the process of installation where the operating system's installer finishes. This is known as provisioning.

Docker: An open source project to pack, ship and run any application as a lightweight container

The functionality of this software somewhat overlaps with that of Vagrant, in which it provides the means to define operating systems installations, but greatly differs in the technology used for this purpose. Docker uses Linux containers, which are not virtual machines per se, but isolated processes running in isolated filesystems. Docker can also use a configuration management system to provision the containers.
```
