---
title: 'Lync Server 2013: Preparazione di Servizi di dominio Active Directory'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
TOCTitle: Preparing Active Directory Domain Services
ms:assetid: 7b0d9aa4-f1ab-4578-b22f-b802b6ed1530
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Gg398607(v=OCS.15)
ms:contentKeyID: 48184583
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 7deb5594c0d3c009ee4b10565bc4dbe12f56d2c4
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981204"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="preparing-active-directory-domain-services-in-lync-server-2013"></a>Preparazione di Servizi di dominio Active Directory in Lync Server 2013

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-02-19_

In Lync Server 2013 è possibile usare la distribuzione guidata di Lync Server per preparare Servizi di dominio Active Directory oppure usare direttamente i cmdlet di Lync Server Management Shell. È anche possibile usare lo strumento della riga di comando LDIFDE. exe direttamente nei controller di dominio, come descritto più avanti in questo argomento.

La distribuzione guidata di Lync Server Guida l'utente attraverso ogni attività di preparazione di Active Directory. La distribuzione guidata esegue i cmdlet di Lync Server Management Shell. Questo strumento è utile per gli ambienti con un singolo dominio e una singola topologia di foresta o altre topologie simili.

<div>


> [!IMPORTANT]  
> È possibile distribuire Lync Server in una foresta o un dominio in cui i controller di dominio eseguono versioni a 32 bit di alcuni sistemi operativi (per informazioni dettagliate, vedere <A href="lync-server-2013-active-directory-infrastructure-requirements.md">requisiti dell'infrastruttura di Active Directory per Lync Server 2013</A>). Tuttavia, non è possibile usare la distribuzione guidata di Lync Server per eseguire la preparazione dello schema, della foresta e del dominio in questi ambienti, perché la distribuzione guidata e i file di supporto sono solo a 64 bit. Puoi invece usare LDIFDE. exe e i file con estensione ldf associati in un controller di dominio a 32 bit per preparare lo schema, la foresta e il dominio. Vedere la sezione "utilizzo di cmdlet e LDIFDE. exe" più avanti in questo argomento.



</div>

Puoi usare i cmdlet di Lync Server Management Shell per eseguire attività in remoto o per ambienti più complessi.

<div>

## <a name="active-directory-preparation-prerequisites"></a>Prerequisiti per la preparazione di Active Directory

È necessario eseguire la procedura di preparazione di Active Directory in un computer che esegue Windows Server 2012, Windows Server 2012 R2 o Windows Server 2008 R2 con SP1 (64 bit). La preparazione di Active Directory richiede Lync Server Management Shell e OCSCore.

Per eseguire le attività di preparazione di Active Directory sono necessari i componenti seguenti:

  - Componenti di base di Lync Server (OCScore. msi)
    
    <div>
    

    > [!NOTE]  
    > Se si prevede di usare Lync Server Management Shell per la preparazione di Active Directory, è necessario eseguire prima di tutto la distribuzione guidata di Lync Server per installare i componenti principali.

    
    </div>

  - Microsoft .NET Framework 4,5
    
    <div>
    

    > [!NOTE]  
    > Per Windows Server 2012 e Windows Server 2012 R2, è possibile installare e attivare .NET Framework 4,5 tramite Server Manager. Per informazioni dettagliate, vedere "Microsoft .NET Framework 4,5" in <A href="lync-server-2013-additional-software-requirements.md">requisiti software aggiuntivi per Lync Server 2013</A>. Per Windows Server&nbsp;2008&nbsp;R2, scaricare e installare <A href="http://www.microsoft.com/en-us/download/details.aspx?id=30653">.NET Framework 4,5</A> dal sito Web Microsoft.

    
    </div>

  - Strumenti di amministrazione remoti del server
    
    <div>
    

    > [!NOTE]  
    > Alcuni strumenti di amministrazione remota sono obbligatori se si eseguono i passaggi di preparazione di Active Directory su un server membro anziché su un controller di dominio. Installare gli snap-in AD DS e gli strumenti della riga di comando e il modulo Active Directory per Windows PowerShell dal nodo strumenti AD DS e AD LDS in Server Manager.

    
    </div>

  - Microsoft Visual C++ 11 ridistribuibile
    
    <div>
    

    > [!NOTE]  
    > Il programma di installazione richiede di installare questo presupposto se non è già installato nel computer. Il pacchetto viene fornito per l'utente e non sarà necessario acquisirlo separatamente.

    
    </div>

  - Windows PowerShell 3,0 (64 bit)
    
    Per Windows Server 2012 e Windows Server 2012 R2, Windows PowerShell 3,0 deve essere incluso nell'installazione di Lync Server 2013. Per Windows Server 2008 R2, è necessario installare o eseguire l'aggiornamento a Windows PowerShell 3,0. Per informazioni dettagliate, vedere [installazione di Windows PowerShell 3,0 per Lync Server 2013](lync-server-2013-installing-windows-powershell-3-0.md)

</div>

<div>

## <a name="administrator-rights-and-roles"></a>Diritti e ruoli di amministratore

La tabella seguente mostra i diritti amministrativi e i ruoli necessari per ogni attività di preparazione di Active Directory.

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
<td><p>Membro del gruppo Schema Admins per il dominio radice della foresta e i diritti di amministratore per il master schema</p></td>
</tr>
<tr class="even">
<td><p>Preparazione della foresta</p></td>
<td><p>Membro del gruppo amministratori aziendali per la foresta</p></td>
</tr>
<tr class="odd">
<td><p>Preparazione del dominio</p></td>
<td><p>Membro del gruppo Amministratori Enterprise o Domain Admins per il dominio specificato</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="active-directory-preparation-cmdlets"></a>Cmdlet di preparazione di Active Directory

Nella tabella seguente vengono confrontati i cmdlet di Lync Server Management Shell usati per preparare Servizi di dominio Active Directory ai comandi LcsCmd usati per preparare Servizi di dominio Active Directory in Microsoft Office Communications Server 2007 R2.

### <a name="cmdlets-compared-to-lcscmd"></a>Cmdlet rispetto a LcsCmd

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
<td><p>LcsCmd/forest/action: SchemaPrep/SchemaType: Server</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdServerSchema</p></td>
<td><p>LcsCmd/forest/action: CheckSchemaPrepState</p></td>
</tr>
<tr class="odd">
<td><p>Enable-CsAdForest</p></td>
<td><p>LcsCmd/forest/action: ForestPrep</p></td>
</tr>
<tr class="even">
<td><p>Disable-CsAdForest</p></td>
<td><p>LcsCmd/forest/action: ForestUnprep</p></td>
</tr>
<tr class="odd">
<td><p>Get-CsAdForest</p></td>
<td><p>LcsCmd/forest/action: CheckForestPrepState</p></td>
</tr>
<tr class="even">
<td><p>Enable-CsAdDomain</p></td>
<td><p>LcsCmd/domain/action: DomainPrep</p></td>
</tr>
<tr class="odd">
<td><p>Disable-CsAdDomain</p></td>
<td><p>LcsCmd/domain/action: DomainUnprep</p></td>
</tr>
<tr class="even">
<td><p>Get-CsAdDomain</p></td>
<td><p>LcsCmd/domain/action: CheckDomainPrepState</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="locked-down-active-directory-requirements"></a>Requisiti di Active Directory bloccati

Se l'ereditarietà delle autorizzazioni è disabilitata o le autorizzazioni dell'utente autenticato devono essere disabilitate nell'organizzazione, è necessario eseguire ulteriori passaggi durante la preparazione del dominio. Per informazioni dettagliate, vedere [preparazione di servizi di dominio Active Directory bloccati in Lync Server 2013](lync-server-2013-preparing-a-locked-down-active-directory-domain-services.md).

</div>

<div>

## <a name="custom-container-permissions"></a>Autorizzazioni contenitore personalizzate

Se l'organizzazione USA contenitori personalizzati anziché i tre contenitori predefiniti, ovvero gli utenti, i computer e i controller di dominio, è necessario concedere l'accesso in lettura ai contenitori personalizzati per il gruppo Authenticated Users. Per la preparazione del dominio è necessaria l'accesso in lettura ai contenitori. Per informazioni dettagliate, vedere [preparazione di domini per Lync Server 2013](lync-server-2013-preparing-domains.md).

</div>

<div>

## <a name="using-cmdlets-and-ldifdeexe"></a>Uso di cmdlet e LDIFDE. exe

Il passaggio **preparazione schema** nella distribuzione guidata di Lync Server e il cmdlet **Install-CsAdServerSchema** estendono lo schema Active Directory nei controller di dominio che gestiscono un sistema operativo a 64 bit. Se è necessario estendere lo schema Active Directory in un controller di dominio che esegue un sistema operativo a 32 bit, è possibile eseguire il cmdlet **Install-CsAdServerSchema** in remoto da un server membro (approccio consigliato). Se è necessario eseguire la preparazione dello schema direttamente sul controller di dominio, è comunque possibile usare lo strumento LDIFDE. exe per importare i file di schema. Lo strumento LDIFDE. exe include la maggior parte delle versioni del sistema operativo Windows.

Se si usa LDIFDE. exe per importare i file di schema, è necessario importare tutti e quattro i file, indipendentemente dal fatto che si stia eseguendo la migrazione da una versione precedente o sia stata eseguita un'installazione pulita. È necessario importarli nella sequenza seguente:

1.  ExternalSchema. ldf

2.  ServerSchema. ldf

3.  BackCompatSchema. ldf

4.  VersionSchema. ldf

<div>


> [!NOTE]  
> I quattro file con estensione ldf si trovano nella directory \Support\Schema del supporto di installazione o del download.



</div>

Per usare LDIFDE. exe per importare i quattro file di schema in un controller di dominio che è lo schema master, usare il formato seguente:

    ldifde -i -v -k -s <DCName> -f <Schema filename> -c DC=X <defaultNamingContext> -j logFilePath -b <administrator account> <logon domain> <password>

Ad esempio:

    ldifde -i -v -k -s DC1 -f ServerSchema.ldf -c DC=X "DC=contoso,DC=com" -j C:\BatchImportLogFile -b Administrator contoso password

<div>


> [!NOTE]  
> Usare il parametro b solo se è stato effettuato l'accesso come utente diverso. Per informazioni dettagliate sui diritti utente necessari, vedere la sezione "diritti e ruoli di amministratore" più indietro in questo argomento.



</div>

Per usare LDIFDE. exe per importare i quattro file di schema in un controller di dominio che non è lo schema master, usare il formato seguente:

    ldifde -i -v -k -s <SchemaMasterFQDN> -f <Schema filename> -c DC=X <rootDomainNamingContext> -j logFilePath -b <administrator account> <domain> <password>

Per informazioni dettagliate sull'uso di LDIFDE, vedere l'articolo 237677 della Microsoft Knowledge Base "utilizzo di LDIFDE per importare ed esportare oggetti directory in Active [http://go.microsoft.com/fwlink/p/?linkId=132204](http://go.microsoft.com/fwlink/p/?linkid=132204)directory".

</div>

<div>

## <a name="in-this-section"></a>Contenuto della sezione

  - [Preparazione dello schema di Active Directory in Lync Server 2013](lync-server-2013-preparing-the-active-directory-schema.md)

  - [Preparazione della foresta per Lync Server 2013](lync-server-2013-preparing-the-forest.md)

  - [Preparazione dei domini per Lync Server 2013](lync-server-2013-preparing-domains.md)

</div>

</div>

<span> </span>

</div>

</div>

</div>

