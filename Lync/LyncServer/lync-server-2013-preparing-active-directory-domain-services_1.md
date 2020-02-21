---
title: 'Lync Server 2013: preparazione di servizi di dominio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: f7c5d83acbe32d33a235e7c2918663340a3ac7ce
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42183759"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Preparazione di servizi di dominio Active Directory in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-02-19_

In Lync Server 2013, è possibile utilizzare la distribuzione guidata di Lync Server per preparare i servizi di dominio Active Directory oppure è possibile utilizzare i cmdlet di Lync Server Management Shell direttamente. È inoltre possibile utilizzare lo strumento da riga di comando ldifde.exe nei controller di dominio, come descritto più avanti in questo argomento.

La distribuzione guidata di Lync Server Guida l'utente attraverso ogni attività di preparazione di Active Directory. La distribuzione guidata esegue i cmdlet di Lync Server Management Shell. Questo strumento è utile per gli ambienti con una topologia a singolo dominio e a singola foresta o con un'altra topologia simile.

<div>


> [!IMPORTANT]  
> È possibile distribuire Lync Server in una foresta o un dominio in cui i controller di dominio eseguono versioni a 32 bit di alcuni sistemi operativi (per informazioni dettagliate, vedere <A href="lync-server-2013-active-directory-infrastructure-requirements.md">Active Directory Infrastructure requirements for Lync Server 2013</A>). Tuttavia, non è possibile utilizzare la distribuzione guidata di Lync Server per eseguire la preparazione dello schema, della foresta e del dominio in questi ambienti perché la distribuzione guidata e i file di supporto sono solo di 64 bit. È tuttavia possibile utilizzare ldifde.exe e i file con estensione ldf associati in un controller di dominio a 32 bit per preparare lo schema, la foresta e il dominio. Vedere la sezione "Utilizzo dei cmdlet e di Ldifde.exe" più avanti in questo argomento.



</div>

È possibile utilizzare i cmdlet di Lync Server Management Shell per eseguire le attività in modalità remota o per ambienti più complessi.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Prerequisiti di preparazione di Active Directory

È necessario eseguire i passaggi di preparazione di Active Directory in un computer che esegue Windows Server 2012, Windows Server 2012 R2 o Windows Server 2008 R2 con SP1 (64 bit). La preparazione di Active Directory richiede Lync Server Management Shell e OCSCore.

Per eseguire le attività di preparazione di Active Directory sono necessari i componenti seguenti:

  - Componenti di base di Lync Server (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Se si prevede di utilizzare Lync Server Management Shell per la preparazione di Active Directory, è necessario eseguire prima la distribuzione guidata di Lync Server per installare i componenti di base.

    
    </div>

  - Microsoft .NET Framework 4.5
    
    <div>
    

    > [!NOTE]  
    > Per Windows Server 2012 e Windows Server 2012 R2, è necessario installare e attivare .NET Framework 4,5 tramite Server Manager. Per informazioni dettagliate, vedere "Microsoft .NET Framework 4,5" in <A href="lync-server-2013-additional-software-requirements.md">Additional Software Requirements for Lync Server 2013</A>. Per Windows Server&nbsp;2008&nbsp;R2, scaricare e installare <A href="https://www.microsoft.com/download/details.aspx?id=30653">.NET Framework 4,5</A> dal sito Web Microsoft.

    
    </div>

  - Strumenti di amministrazione remota del server
    
    <div>
    

    > [!NOTE]  
    > Se si eseguono le attività di preparazione di Active Directory in un server membro anziché in un controller di dominio, sono necessari alcuni strumenti inclusi in Strumenti di amministrazione remota del server. Installare gli snap-in di AD DS e gli strumenti da riga di comando e il modulo di Active Directory per Windows PowerShell dal nodo AD DS e AD LDS Tools in Server Manager.

    
    </div>

  - Microsoft Visual C++ 11 Redistributable
    
    <div>
    

    > [!NOTE]  
    > Se il componente non è già presente nel computer, nel corso dell'installazione viene richiesto di installare questo prerequisito. Il pacchetto è fornito in dotazione e non è necessario acquistarlo separatamente.

    
    </div>

  - Windows PowerShell 3,0 (64 bit)
    
    Per Windows Server 2012 e Windows Server 2012 R2, Windows PowerShell 3,0 deve essere incluso nell'installazione di Lync Server 2013. Per Windows Server 2008 R2, è necessario installare o eseguire l'aggiornamento a Windows PowerShell 3,0. Per informazioni dettagliate, vedere [Installing Windows PowerShell 3,0 for Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Diritti e ruoli amministrativi

Nella tabella seguente vengono indicati i diritti e i ruoli amministrativi necessari per ogni attività di preparazione di Active Directory.

### <a name="user-rights-required-for-active-directory-preparation"></a>Diritti utente necessari per la preparazione di Active Directory

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Procedura</th>
<th>Diritti o ruoli</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Preparazione dello schema</p></td>
<td><p>Membro del gruppo Schema Admins per il dominio radice della foresta e diritti di amministratore per il master schema</p></td>
</tr>
<tr class="even">
<td><p>Preparazione della foresta</p></td>
<td><p>Membro del gruppo Enterprise Admins della foresta</p></td>
</tr>
<tr class="odd">
<td><p>Preparazione del dominio</p></td>
<td><p>Membro del gruppo Enterprise Admins o Domain Admins per il dominio specificato</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlet per la preparazione di Active Directory

Nella tabella seguente vengono confrontati i cmdlet di Lync Server Management Shell utilizzati per preparare Servizi di dominio Active Directory ai comandi LcsCmd utilizzati per preparare Servizi di dominio Active Directory in Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Confronto tra cmdlet e LcsCmd

<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Cmdlet</th>
<th>LcsCmd</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Install-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:SchemaPrep /SchemaType:Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>Lcscmd /forest /action:CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>Lcscmd /forest /action:CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>Lcscmd /domain /action:CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Requisiti per un ambiente Active Directory bloccato

Se l'ereditarietà delle autorizzazioni è disabilitata o è necessario disabilitare le autorizzazioni degli utenti autenticati nell'organizzazione, durante la preparazione del dominio sono necessari alcuni passaggi aggiuntivi. Per ulteriori informazioni, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Autorizzazioni per contenitori personalizzati

Se nell'organizzazione vengono utilizzati contenitori personalizzati anziché tre contenitori incorporati (ovvero utenti, computer e controller di dominio), è necessario concedere l'accesso in lettura ai contenitori personalizzati per il gruppo Authenticated Users. L'accesso in lettura ai contenitori è necessario per la preparazione del dominio. Per ulteriori informazioni, vedere [preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Utilizzo dei cmdlet e di Ldifde.exe

Il passaggio di **preparazione dello schema** nella distribuzione guidata di Lync Server e il cmdlet **Install-CsAdServerSchema** estendono lo schema di Active Directory sui controller di dominio che eseguono un sistema operativo a 64 bit. Se è necessario estendere lo schema di Active Directory in un controller di dominio che esegue un sistema operativo a 32 bit, è possibile utilizzare il cmdlet **Install-CsAdServerSchema** in remoto da un server membro (procedura consigliata). Se è necessario eseguire la preparazione dello schema direttamente nel controller di dominio, è tuttavia possibile utilizzare lo strumento Ldifde.exe per importare i file di schema. Lo strumento Ldifde.exe è incluso nella maggior parte delle versioni del sistema operativo Windows.

Se si utilizza o strumento Ldifde.exe per importare i file di schema è necessario importare tutti e quattro i file, indipendentemente dal fatto che si stia eseguendo la migrazione da una versione precedente oppure un'installazione pulita. I file vanno importati nell'ordine seguente:

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> I quattro file con estensione ldf si trovano nella directory \Support\Schema del supporto di installazione o del download.



</div>

Per utilizzare Ldifde.exe per importare i quattro file di schema in un controller di dominio che funge da master schema, utilizzare il formato seguente:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Ad esempio:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Utilizzare il parametro b solo se si è effettuato l'accesso come un altro utente. Per informazioni dettagliate sui diritti utente necessari, vedere la sezione "Diritti e ruoli amministrativi" in precedenza in questo argomento.



</div>

Per utilizzare Ldifde.exe per importare i quattro file di schema in un controller di dominio che non funge da master schema, utilizzare il formato seguente:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Per informazioni dettagliate sull'utilizzo di LDIFDE, vedere l'articolo 237677 della Microsoft Knowledge Base "using LDIFDE to Import and Export Directory Objects to Active [https://go.microsoft.com/fwlink/p/?linkId=132204](https://go.microsoft.com/fwlink/p/?linkid=132204)directory".

</div>

<div>

## <a name="in-this-section"></a>Argomenti della sezione

  - [Preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Preparazione della foresta per Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

