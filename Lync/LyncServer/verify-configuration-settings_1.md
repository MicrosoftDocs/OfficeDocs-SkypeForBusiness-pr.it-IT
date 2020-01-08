---
title: Verificare impostazioni di configurazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: a20b78ac9275657461beb74a7325c0c46e4e40fd
ms.sourcegitcommit: bb53f131fabb03a66f0d000f8ba668fbad190778
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/11/2019
ms.locfileid: "40981222"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Verificare impostazioni di configurazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2012-09-28_

Dopo aver merge la topologia ed eseguito il cmdlet **Import-CsLegacyConfiguration** , verificare che i criteri e le impostazioni di Office Communications Server 2007 R2 siano stati importati in Lync Server 2013. Nella tabella seguente sono elencati i criteri e le impostazioni da verificare.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Criteri e impostazioni per verificare dopo la migrazione


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se si usa questo carico di lavoro:</th>
<th>Verificare questi criteri e impostazioni:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Messaggistica istantanea (IM) e servizi di conferenza</p></td>
<td><p>Criteri di presenza</p>
<p>Criteri di conferenza</p></td>
</tr>
<tr class="even">
<td><p>Chiamate in conferenza</p></td>
<td><p>Numeri di accesso esterno</p>
<p>Dial plan</p></td>
</tr>
<tr class="odd">
<td><p>VoIP aziendale</p></td>
<td><p>Criteri vocali</p>
<p>Route vocali</p>
<p>Dial plan</p>
<p>Impostazioni di utilizzo PSTN</p></td>
</tr>
<tr class="even">
<td><p>Communicator Web Access</p></td>
<td><p>URL semplici</p></td>
</tr>
<tr class="odd">
<td><p>Utenti esterni</p></td>
<td><p>Criteri di accesso esterno</p></td>
</tr>
<tr class="even">
<td><p>Archiviazione</p></td>
<td><p>Criteri di archiviazione</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>Per verificare i criteri e le impostazioni

1.  Nell'ambiente Office Communications Server 2007 R2 prendere nota dei nomi dei dial plan (in precedenza noti come profili di posizione), numeri di accesso in ingresso (numeri di telefono e aree geografiche di accesso per i servizi di conferenza), route vocali e criteri elencati nell'elenco tabella precedente, oltre agli URL usati per Communicator Web Access.

2.  Nel server front-end di Lync Server 2013 aprire il pannello di controllo di Lync Server.

3.  Per verificare i criteri di conferenza importati, nel riquadro sinistro fare clic su servizi di **conferenza**, su **criteri di conferenza**e quindi verificare che tutti i criteri di conferenza nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.
    
    <div>
    

    > [!NOTE]  
    > Il criterio della <STRONG>riunione</STRONG> delle versioni precedenti di Office Communications Server è ora noto come criterio di conferenza in Lync Server 2013. Inoltre, l'impostazione <STRONG>Particpants anonima</STRONG> delle versioni precedenti di Office Communications Server è ora un'impostazione nei criteri di conferenza di Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > In Office Communications Server 2007 R2, se i criteri di conferenza non sono impostati per l' <STRONG>uso per utente</STRONG>, vengono importate solo le impostazioni dei criteri globali. In questa situazione non vengono importati altri criteri di conferenza.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Se <STRONG>i partecipanti anonimi</STRONG> sono impostati per l' <STRONG>applicazione per ogni utente</STRONG> nei criteri di conferenza di Office Communications Server 2007 R2, vengono creati due criteri di conferenza durante la migrazione: uno con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> impostato su <STRONG>true</STRONG> e uno con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> impostato su <STRONG>false</STRONG>.

    
    </div>

4.  Per verificare i piani di chiamata importati, fare clic su **routing vocale**, fare clic su **dial plan**e verificare che tutti i dial plan nell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.
    
    <div>
    

    > [!NOTE]  
    > In Lync Server 2013 i <STRONG>profili di posizione</STRONG> sono ora indicati come <STRONG>dial-plan</STRONG>.

    
    </div>

5.  Per verificare i criteri vocali importati, fare clic su **routing vocale**, fare clic su **criteri vocali**e verificare che tutti i criteri vocali nell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.
    
    <div>
    

    > [!NOTE]  
    > Se il criterio vocale non è impostato per l' <STRONG>uso per utente</STRONG> nell'ambiente Office Communications Server 2007 R2, vengono importate solo le impostazioni dei criteri globali. In questa situazione non vengono importati altri criteri vocali.

    
    </div>

6.  Per verificare le route vocali importate, fare clic su **routing vocale**, fare clic su **Route**e verificare che tutte le route vocali nell'ambiente Office Communicator 2007 R2 siano incluse nell'elenco.

7.  Per verificare le impostazioni di utilizzo PSTN importate, fare clic su **routing vocale**, fare clic su **utilizzo PSTN**e verificare che le impostazioni di utilizzo PSTN dell'ambiente Office Communicator 2007 R2 siano incluse nell'elenco.

8.  Per verificare i criteri di accesso esterno importati, fare clic su **Federazione e accesso esterno**, fare clic su **criteri di accesso esterno**e verificare che tutti i criteri di accesso esterno nell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.

9.  Per verificare i criteri di archiviazione, fare clic su **monitoraggio e archiviazione**, fare clic su **criteri di archiviazione**e verificare che tutti i criteri di archiviazione nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.

10. Aprire Lync Server Management Shell.

11. Per verificare i criteri di presenza, nella riga di comando digitare quanto segue:
    
        Get-CsPresencePolicy
    
    Esaminando il nome nel parametro **Identity** , verificare che siano stati importati tutti i criteri di presenza nell'ambiente Office Communications Server 2007 R2.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Per verificare i criteri e le impostazioni usando i cmdlet

1.  Aprire Lync Server Management Shell.

2.  Eseguire i cmdlet nella tabella seguente per verificare i criteri e le impostazioni.
    
    La sintassi di questi cmdlet è simile all'esempio seguente:
    
        Get-CsConferencingPolicy
    
    Per informazioni dettagliate su questi cmdlet, eseguire:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Per questo criterio o impostazione:</th>
<th>Utilizzare questo cmdlet:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criteri di presenza</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Criteri di conferenza</p></td>
<td><p><strong>Get-CsConferencingPolicy</strong></p></td>
</tr>
<tr class="odd">
<td><p>Numeri di accesso esterno</p></td>
<td><p><strong>Get-CsDialInConferencingAccessNumber</strong></p></td>
</tr>
<tr class="even">
<td><p>Dial plan</p></td>
<td><p><strong>Get-CsDialPlan</strong></p></td>
</tr>
<tr class="odd">
<td><p>Criteri vocali</p></td>
<td><p><strong>Get-CsVoicePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Route vocali</p></td>
<td><p><strong>Get-CsVoiceRoute</strong></p></td>
</tr>
<tr class="odd">
<td><p>Utilizzo PSTN</p></td>
<td><p><strong>Get-CsPstnUsage</strong></p></td>
</tr>
<tr class="even">
<td><p>URL</p></td>
<td><p><strong>Get-CsSimpleUrlConfiguration</strong></p></td>
</tr>
<tr class="odd">
<td><p>Criteri di accesso esterno</p></td>
<td><p><strong>Get-CsExternalAccessPolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Criteri di archiviazione</p></td>
<td><p><strong>Get-CsArchivingPolicy</strong></p></td>
</tr>
</tbody>
</table>


</div>

</div>

<span> </span>

</div>

</div>

</div>

