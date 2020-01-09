---
title: 'Lync Server 2013: Configurazione di IIS'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: IIS configuration
ms:assetid: b458babf-bf64-43f0-8a8e-612f5096b63c
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg412871(v=OCS.15)
ms:contentKeyID: 48185169
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 29b9803fdb6c4a048fdf072b5ba2e5722b863640
ms.sourcegitcommit: 2cc98fcecd753e6e8374fc1b5a78b8e3d61e0cf7
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40992101"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="iis-configuration-in-lync-server-2013"></a>Configurazione di IIS in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-17_

Per completare correttamente questa procedura, è necessario avere effettuato l'accesso al server come amministratore locale e un utente di dominio.

Prima di configurare e installare il front end server per Lync Server 2013, Standard Edition o il primo server front-end in un pool, è possibile installare e configurare il ruolo del server e i servizi Web per Internet Information Services (IIS).

<div class=" ">


> [!IMPORTANT]  
> Se l'organizzazione richiede l'individuazione di IIS e tutti i servizi Web in un'unità diversa da quella dell'unità di sistema, è possibile modificare il percorso della posizione di installazione per i file di Lync Server 2013 nella finestra di dialogo Imposta durante l'installazione iniziale di Lync Server 2013 Strumenti di amministrazione. Gli strumenti di amministrazione vengono installati prima dell'installazione di IIS. Se si installano i file di configurazione in questo percorso, incluso OCSCore. msi, anche il resto dei file di Lync Server 2013 verrà distribuito nell'unità. Per Dtails, vedere <A href="lync-server-2013-install-lync-server-administrative-tools.md">installare gli strumenti di amministrazione di Lync Server 2013</A>. Per informazioni dettagliate su come rilocare il INETPUB distribuito da Windows Server Manager durante l'installazione di <A href="http://go.microsoft.com/fwlink/p/?linkid=216888">http://go.microsoft.com/fwlink/p/?linkId=216888</A>IIS, vedere.



</div>

La tabella seguente indica i servizi ruolo di IIS 7,5 necessari.

### <a name="iis-75-role-services"></a>Servizi ruolo di IIS 7,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Titolo del ruolo</th>
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
<td><p>Sviluppo di applicazioni</p></td>
<td><p>ASP.NET</p>
<p>Windows Server 2012 richiede anche ASP. NET 4.5</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Estensibilità .NET</p></td>
</tr>
<tr class="even">
<td><p>Sviluppo di applicazioni</p></td>
<td><p>Estensioni ISAPI (Internet Server API)</p></td>
</tr>
<tr class="odd">
<td><p>Sviluppo di applicazioni</p></td>
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
<td><p>Traccia</p></td>
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
<td><p>Autenticazione del mapping dei certificati client</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>Filtro delle richieste</p></td>
</tr>
<tr class="odd">
<td><p>Prestazioni</p></td>
<td><p>Compressione del contenuto statico</p>
<p>Compressione del contenuto dinamico</p></td>
</tr>
<tr class="even">
<td><p>Strumenti di gestione</p></td>
<td><p>Console di gestione di IIS</p></td>
</tr>
<tr class="odd">
<td><p>Strumenti di gestione</p></td>
<td><p>Script e strumenti di gestione di IIS</p></td>
</tr>
</tbody>
</table>


Nel sistema operativo Windows Server 2008 R2 SP1 x64 è possibile usare Windows PowerShell 2,0. È prima di tutto necessario importare il modulo ServerManager e quindi installare il ruolo e i servizi ruolo di IIS 7,5.

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Scripting-Tools, Web-Windows-Auth, Web-Asp-Net, Web-Log-Libraries, Web-Http-Tracing, Web-Stat-Compression, Web-Dyn-Compression, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Errors, Web-Http-Logging, Web-Net-Ext, Web-Client-Auth, Web-Filtering, Web-Mgmt-Console
   ```

<div class=" ">


> [!NOTE]  
> Per impostazione predefinita, l'autenticazione anonima viene installata con il ruolo del server IIS. È possibile gestire l'autenticazione anonima dopo l'installazione di IIS. Per informazioni dettagliate, vedere "abilitare l'autenticazione anonima (IIS 7 <A href="http://go.microsoft.com/fwlink/p/?linkid=203935">http://go.microsoft.com/fwlink/p/?linkId=203935</A>)" all'indirizzo.



</div>

La tabella seguente indica i servizi ruolo di IIS 8,0 e IIS 8,5 necessari per Windows Server 2012 e Windows Server 2012 R2.

<div class=" ">


> [!NOTE]  
> Per Windows Server 2012 e Windows Server 2012 R2, il cmdlet Add-WindowsFeature è stato sostituito dal cmdlet Install-WindowsFeature. Per informazioni dettagliate, vedere <A href="http://go.microsoft.com/fwlink/p/?linkid=392274">Install-WindowsFeature</A>.



</div>

### <a name="iis-80-and-iis-85-role-services"></a>Servizi ruolo di IIS 8,0 e IIS 8,5

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Titolo del ruolo</th>
<th>Servizio ruolo</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Server Web (IIS)</p></td>
<td><p>Server Web</p></td>
</tr>
<tr class="even">
<td><p>Caratteristiche HTTP comuni</p></td>
<td><p>Documento predefinito</p></td>
</tr>
<tr class="odd">
<td><p>Caratteristiche HTTP comuni</p></td>
<td><p>Esplorazione della directory</p></td>
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
<td><p>Richiedi monitor</p></td>
</tr>
<tr class="even">
<td><p>Integrità e diagnostica</p></td>
<td><p>Traccia</p></td>
</tr>
<tr class="odd">
<td><p>Sicurezza</p></td>
<td><p>Filtro delle richieste</p></td>
</tr>
<tr class="even">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione di base</p></td>
</tr>
<tr class="odd">
<td><p>Sicurezza</p></td>
<td><p>Autenticazione del mapping dei certificati client</p></td>
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
<td><p>Lato server include</p></td>
</tr>
<tr class="even">
<td><p>Strumenti di gestione</p></td>
<td><p>Console di gestione di IIS</p></td>
</tr>
<tr class="odd">
<td><p>Strumenti di gestione</p></td>
<td><p>Compatibilità della metabase di IIS 6</p></td>
</tr>
<tr class="even">
<td><p>Strumenti di gestione</p></td>
<td><p>Script e strumenti di gestione di IIS</p></td>
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
<td><p>Condivisione della porta TCP</p></td>
</tr>
<tr class="even">
<td><p>Servizio trasferimento intelligente in background</p></td>
<td><p>Estensioni del server IIS</p></td>
</tr>
<tr class="odd">
<td><p>Servizi a penna e grafia</p></td>
<td><p>Servizi a penna e grafia</p></td>
</tr>
<tr class="even">
<td><p>Media Foundation</p></td>
<td><p>Media Foundation</p></td>
</tr>
<tr class="odd">
<td><p>Interfacce utente e infrastruttura</p></td>
<td><p>Strumenti e infrastrutture di gestione grafica</p></td>
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
<td><p>Servizio di attivazione processo Windows</p></td>
<td><p>Modello di processo</p></td>
</tr>
<tr class="even">
<td><p>Servizio di attivazione processo Windows</p></td>
<td><p>API di configurazione</p></td>
</tr>
</tbody>
</table>


In Windows Server 2012 e Windows Server 2012 R2 è possibile usare Windows PowerShell 3,0 per installare i requisiti di IIS. Usando il modulo ServerManager in Windows PowerShell 3,0, digitare:

   ```PowerShell
    Import-Module ServerManager
   ```

   ```PowerShell
    Add-WindowsFeature Web-Server, Web-Static-Content, Web-Default-Doc, Web-Http-Errors, Web-Asp-Net, Web-Net-Ext, Web-ISAPI-Ext, Web-ISAPI-Filter, Web-Http-Logging, Web-Log-Libraries, Web-Request-Monitor, Web-Http-Tracing, Web-Basic-Auth, Web-Windows-Auth, Web-Client-Auth, Web-Filtering, Web-Stat-Compression, Web-Dyn-Compression, NET-Framework-45-Core, NET-WCF-HTTP-Activation45, Web-Asp-Net45, Web-Mgmt-Tools, Web-Scripting-Tools, Web-Mgmt-Console, Web-Mgmt-Compat, Windows-Identity-Foundation, Server-Media-Foundation, BITS -Source D:\sources\sxs
   ```

<div class=" ">


> [!IMPORTANT]  
> Nuovo con Windows Server 2012 è il parametro – source che definisce la posizione in cui è possibile trovare il file multimediale di origine di Windows Server 2012. Il contenuto multimediale può essere definito come unità DVD (ad esempio, D:\Sources\Sxs) o in una condivisione di rete che i file multimediali sono stati copiati (ad esempio \\, fileserver\windows2012\sources\Sxs).



</div>

<div>

## <a name="see-also"></a>Vedere anche


[Requisiti di IIS per pool Front End e server Standard Edition in Lync Server 2013](lync-server-2013-iis-requirements-for-front-end-pools-and-standard-edition-servers.md)  
  

</div>

</div>

<span> </span>

</div>

</div>

</div>

