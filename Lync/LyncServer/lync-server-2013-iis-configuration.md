---
title: 'Lync Server 2013: configurazione di IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 1fc8895a144b4911560af8fd6a2f12d576f3ec14
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48528153"
---
# <a name="iis-configuration-in-lync-server-2013"></a>Configurazione di IIS in Lync Server 2013

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-17_

Per eseguire questa procedura, è necessario aver eseguito l'accesso al server almeno come amministratore locale e utente di dominio.

Prima di configurare e installare il front end server per Lync Server 2013, Standard Edition o il primo front end server in un pool, è necessario installare e configurare il ruolo del server e i servizi Web per Internet Information Services (IIS).

<div class=" ">


> [!IMPORTANT]  
> Se l'organizzazione richiede l'individuazione di IIS e di tutti i servizi Web in un'unità diversa dall'unità di sistema, è possibile modificare il percorso di installazione dei file di Lync Server 2013 nella finestra di dialogo Imposta quando si installano inizialmente gli strumenti di amministrazione di Lync Server 2013. È possibile installare gli strumenti di amministrazione prima di installare IIS. Se si installano i file di installazione in questo percorso, incluso OCSCore.msi, anche il resto dei file di Lync Server 2013 verrà distribuito in questa unità. Per Dtails, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">installare gli strumenti di amministrazione di Lync Server 2013</A>. Per informazioni dettagliate su come spostare il INETPUB distribuito da Windows Server Manager durante l'installazione di IIS, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=216888">https://go.microsoft.com/fwlink/p/?linkId=216888</A> .



</div>

Nella tabella seguente sono indicati i servizi di ruolo IIS 7,5 necessari.

### <a name="iis-75-role-services"></a>Servizi ruolo di IIS 7,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Intestazione ruolo</th>
<th>Servizio ruolo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Funzionalità HTTP comuni installate</p></td>
<td><p>Contenuto statico</p></td>
</tr>
<tr class="even">
<td><p>Funzionalità HTTP comuni installate</p></td>
<td><p>Documento predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Funzionalità HTTP comuni installate</p></td>
<td><p>Errori HTTP</p></td>
</tr>
<tr class="even">
<td><p>Sviluppo applicazioni</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 richiede anche ASP. NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo applicazioni</p></td>
<td><p>Estendibilità .NET</p></td>
</tr>
<tr class="even">
<td><p>Sviluppo applicazioni</p></td>
<td><p>Estensioni ISAPI (Internet Server API)</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo applicazioni</p></td>
<td><p>Filtri ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Integrità e diagnostica</p></td>
<td><p>Registrazione HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Integrità e diagnostica</p></td>
<td><p>Strumenti di registrazione</p></td>
</tr>
<tr class="even">
<td><p>Integrità e diagnostica</p></td>
<td><p>Analisi della</p></td>
</tr>
<tr class="odd">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione anonima (installata e abilitata per impostazione predefinita)</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione di Windows</p></td>
</tr>
<tr class="odd">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione mapping certificati client</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>Filtro richieste</p></td>
</tr>
<tr class="odd">
<td><p>Prestazioni</p></td>
<td><p>Compressione contenuto statico</p>
<p>Compressione del contenuto dinamico</p></td>
</tr>
<tr class="even">
<td><p>Strumenti di gestione</p></td>
<td><p>Console di gestione IIS</p></td>
</tr>
<tr class="odd">
<td><p>Strumenti di gestione</p></td>
<td><p>Strumenti e script di gestione IIS</p></td>
</tr>
</tbody>
</table>


Nel sistema operativo Windows Server 2008 R2 SP1 x64, è possibile utilizzare Windows PowerShell 2,0. È prima necessario importare il modulo ServerManager e quindi installare il ruolo e i servizi ruolo di IIS 7.5.

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> L'autenticazione anonima viene installata per impostazione predefinita con il ruolo del server IIS. È possibile gestire l'autenticazione anonima dopo l'installazione di IIS. Per informazioni dettagliate, vedere la sezione relativa all'abilitazione dell'autenticazione anonima (IIS 7) all'indirizzo <A href="https://go.microsoft.com/fwlink/p/?linkid=203935">https://go.microsoft.com/fwlink/p/?linkId=203935</A> .



</div>

Nella tabella seguente sono indicati i servizi di ruolo IIS 8,0 e IIS 8,5 necessari per Windows Server 2012 e Windows Server 2012 R2.

<div class=" ">


> [!NOTE]  
> Per Windows Server 2012 e Windows Server 2012 R2, il cmdlet Add-WindowsFeature è stato sostituito dal cmdlet Install-WindowsFeature. Per informazioni dettagliate, vedere <A href="https://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>Servizi ruolo IIS 8,0 e IIS 8,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Intestazione ruolo</th>
<th>Servizio ruolo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Web Server (IIS)</p></td>
<td><p>Server Web</p></td>
</tr>
<tr class="even">
<td><p>Caratteristiche HTTP comuni</p></td>
<td><p>Documento predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Caratteristiche HTTP comuni</p></td>
<td><p>Esplorazione directory</p></td>
</tr>
<tr class="even">
<td><p>Caratteristiche HTTP comuni</p></td>
<td><p>Errori HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Caratteristiche HTTP comuni</p></td>
<td><p>Contenuto statico</p></td>
</tr>
<tr class="even">
<td><p>Caratteristiche HTTP comuni</p></td>
<td><p>Reindirizzamento HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Integrità e diagnostica</p></td>
<td><p>Registrazione HTTP</p></td>
</tr>
<tr class="even">
<td><p>Integrità e diagnostica</p></td>
<td><p>Strumenti di registrazione</p></td>
</tr>
<tr class="odd">
<td><p>Integrità e diagnostica</p></td>
<td><p>Monitor richieste</p></td>
</tr>
<tr class="even">
<td><p>Integrità e diagnostica</p></td>
<td><p>Analisi della</p></td>
</tr>
<tr class="odd">
<td><p>Sicurezza</p></td>
<td><p>Filtro richieste</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione di base</p></td>
</tr>
<tr class="odd">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione mapping certificati client</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione di Windows</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Estensibilità .NET 3,5</p></td>
</tr>
<tr class="even">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Estensibilità .NET 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>ASP.Net 3,5</p></td>
</tr>
<tr class="even">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Estensioni ISAPI</p></td>
</tr>
<tr class="even">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Filtri ISAPI</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Inclusioni sul lato server</p></td>
</tr>
<tr class="even">
<td><p>Strumenti di gestione</p></td>
<td><p>Console di gestione IIS</p></td>
</tr>
<tr class="odd">
<td><p>Strumenti di gestione</p></td>
<td><p>Compatibilità della metabase di IIS 6</p></td>
</tr>
<tr class="even">
<td><p>Strumenti di gestione</p></td>
<td><p>Strumenti e script di gestione IIS</p></td>
</tr>
<tr class="odd">
<td><p>Caratteristiche di .NET 3,5 Framework</p></td>
<td><p>.NET 3,5 Framework</p></td>
</tr>
<tr class="even">
<td><p>Caratteristiche di .NET 4,5 Framework</p></td>
<td><p>.NET Framework 4,5</p></td>
</tr>
<tr class="odd">
<td><p>Caratteristiche di .NET 4,5 Framework</p></td>
<td><p>ASP.Net 4,5</p></td>
</tr>
<tr class="even">
<td><p>Caratteristiche di .NET 4,5 Framework</p></td>
<td><p>Attivazione HTTP</p></td>
</tr>
<tr class="odd">
<td><p>Caratteristiche di .NET 4,5 Framework</p></td>
<td><p>Condivisione delle porte TCP</p></td>
</tr>
<tr class="even">
<td><p>Servizio di trasferimento intelligente in background</p></td>
<td><p>Estensioni del server IIS</p></td>
</tr>
<tr class="odd">
<td><p>Servizi di riconoscimento della grafia</p></td>
<td><p>Servizi di riconoscimento della grafia</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Interfacce utente e infrastruttura</p></td>
<td><p>Strumenti e infrastruttura di gestione grafica</p></td>
</tr>
<tr class="even">
<td><p>Interfacce utente e infrastruttura</p></td>
<td><p>Esperienza desktop</p></td>
</tr>
<tr class="odd">
<td><p>Interfacce utente e infrastruttura</p></td>
<td><p>Shell grafica del server</p></td>
</tr>
<tr class="even">
<td><p>Windows Identity Foundation 3,5</p></td>
<td><p>Windows Identity Foundation 3,5</p></td>
</tr>
<tr class="odd">
<td><p>Servizio di attivazione del processo di Windows</p></td>
<td><p>Modello di processo</p></td>
</tr>
<tr class="even">
<td><p>Servizio di attivazione del processo di Windows</p></td>
<td><p>API di configurazione</p></td>
</tr>
</tbody>
</table>


In Windows Server 2012 e Windows Server 2012 R2, è possibile utilizzare Windows PowerShell 3,0 per installare i requisiti di IIS. Se si utilizza il modulo ServerManager in Windows PowerShell 3,0, digitare quanto segue:

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Nuovo con Windows Server 2012 è il parametro – source che definisce la posizione in cui è possibile trovare il file multimediale di origine di Windows Server 2012. Il supporto può essere definito come un'unità DVD (ad esempio, D:\Sources\Sxs) o in una condivisione di rete che i file multimediali sono stati copiati (ad esempio, \\ fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti di IIS per pool Front end e server Standard Edition in Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

