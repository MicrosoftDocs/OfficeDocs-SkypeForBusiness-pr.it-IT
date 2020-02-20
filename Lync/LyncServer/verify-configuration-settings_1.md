---
title: Verificare le impostazioni di configurazione
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: Verify configuration settings
ms:assetid: 41dbf91c-f2e1-4b9a-88cf-959575558cf2
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204848(v=OCS.15)
ms:contentKeyID: 48183997
ms.date: 07/23/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 40beac1b249b09ef493b7f95cbb9380b307eda63
ms.sourcegitcommit: 33db8c7febd4cf1591e8dcbbdfd6fc8e8925896e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/19/2020
ms.locfileid: "42147899"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="verify-configuration-settings"></a>Verificare le impostazioni di configurazione

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2012-09-28_

Dopo aver unito la topologia ed eseguito il cmdlet **Import-CsLegacyConfiguration** , verificare che i criteri e le impostazioni di Office Communications Server 2007 R2 siano stati importati in Lync Server 2013. Nella tabella seguente sono elencati i criteri e le impostazioni da verificare.

<div>

## <a name="policies-and-settings-to-verify-after-migration"></a>Criteri e impostazioni da verificare dopo la migrazione


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Se si usa il carico di lavoro seguente:</th>
<th>Verificare i criteri e le impostazioni seguenti:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Servizi di messaggistica istantanea e conferenza</p></td>
<td><p>Criteri di presenza</p>
<p>Criteri di conferenza</p></td>
</tr>
<tr class="even">
<td><p>Conferenza telefonica con accesso esterno</p></td>
<td><p>Numeri di accesso esterno</p>
<p>Dial plan</p></td>
</tr>
<tr class="odd">
<td><p>VoIP aziendale</p></td>
<td><p>Criterio vocale</p>
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
<td><p>Criterio di archiviazione</p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="to-verify-policies-and-settings"></a>Per verificare i criteri e le impostazioni

1.  Nell'ambiente Office Communications Server 2007 R2, prendere nota dei nomi dei dial plan (in precedenza noti come profili località), i numeri di accesso esterno (i numeri di telefono di accesso e le aree geografiche), le route vocali e i criteri elencati nel tabella precedente, oltre agli URL utilizzati per Communicator Web Access.

2.  Nel server Lync Server 2013 front end, aprire il pannello di controllo di Lync Server.

3.  Per verificare i criteri di conferenza importati, nel riquadro sinistro **fare clic su servizi di conferenza,** su **criteri conferenza**e quindi verificare che nell'elenco siano inclusi tutti i criteri di conferenza nell'ambiente Office Communications Server 2007 R2.
    
    <div>
    

    > [!NOTE]  
    > Il criterio di <STRONG>riunione</STRONG> delle versioni precedenti di Office Communications Server è ora noto come criterio di conferenza in Lync Server 2013. Inoltre, l'impostazione <STRONG>Particpants anonima</STRONG> dalle versioni precedenti di Office Communications Server è ora un'impostazione nei criteri di conferenza di Lync Server 2013.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > In Office Communications Server 2007 R2, se i criteri di conferenza non sono impostati per l' <STRONG>utilizzo per utente</STRONG>, vengono importate solo le impostazioni dei criteri globali. In questa situazione non vengono importati altri criteri conferenza.

    
    </div>
    
    <div>
    

    > [!NOTE]  
    > Se <STRONG>i partecipanti anonimi</STRONG> sono impostati su <STRONG>Applica per utente</STRONG> nei criteri di conferenza di Office Communications Server 2007 R2, vengono creati due criteri di conferenza durante la migrazione: uno con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> impostato su <STRONG>true</STRONG> e uno con <STRONG>AllowAnonymousParticipantsInMeetings</STRONG> impostato su <STRONG>false</STRONG>.

    
    </div>

4.  Per verificare i dial plan importati, fare clic su **Routing vocale**, su **Dial Plan** e quindi verificare che tutti i dial plan dell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.
    
    <div>
    

    > [!NOTE]  
    > In Lync Server 2013, i <STRONG>profili località</STRONG> sono ora denominati <STRONG>dial plan</STRONG>.

    
    </div>

5.  Per verificare i criteri vocali importati, fare clic su **Routing vocale**, su **Criteri vocali** e quindi verificare che tutti i criteri vocali dell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.
    
    <div>
    

    > [!NOTE]  
    > Se il criterio vocale non è impostato per l' <STRONG>utilizzo per utente</STRONG> nell'ambiente Office Communications Server 2007 R2, vengono importate solo le impostazioni dei criteri globali. In questa situazione non vengono importati altri criteri vocali.

    
    </div>

6.  Per verificare le route vocali importate, fare clic su **Routing vocale**, su **Route** e quindi verificare che tutte le route vocali dell'ambiente Office Communicator 2007 R2 siano incluse nell'elenco.

7.  Per verificare le impostazioni di utilizzo PSTN importate, fare clic su **Routing vocale**, su **Utilizzo PSTN** e quindi verificare che le impostazioni di utilizzo PSTN dell'ambiente Office Communicator 2007 R2 siano incluse nell'elenco.

8.  Per verificare i criteri di accesso esterno importati, fare clic su **Federazione e accesso esterno**, su **Criteri di accesso esterno** e quindi verificare che tutti i criteri di accesso esterno dell'ambiente Office Communicator 2007 R2 siano inclusi nell'elenco.

9.  Per verificare i criteri di archiviazione, fare clic su **monitoraggio e archiviazione**, su **criteri di archiviazione**e quindi verificare che tutti i criteri di archiviazione nell'ambiente Office Communications Server 2007 R2 siano inclusi nell'elenco.

10. Aprire Lync Server Management Shell.

11. Per verificare i criteri di presenza, alla riga di comando digitare quanto segue.
    
        Get-CsPresencePolicy
    
    Esaminando il nome nel parametro **Identity** , verificare che siano stati importati tutti i criteri di presenza nell'ambiente Office Communications Server 2007 R2.

</div>

<div>

## <a name="to-verify-policies-and-settings-by-using-cmdlets"></a>Per verificare i criteri e le impostazioni utilizzando i cmdlet

1.  Aprire Lync Server Management Shell.

2.  Eseguire i cmdlet nella tabella seguente per verificare i criteri e le impostazioni.
    
    La sintassi di tali cmdlet è simile all'esempio seguente:
    
        Get-CsConferencingPolicy
    
    Per informazioni dettagliate su tali cmdlet, eseguire:
    
        Get-Help <cmdlet name> -Detailed


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Per i criteri o le impostazioni seguenti:</th>
<th>Usare il cmdlet seguente:</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Criteri di presenza</p></td>
<td><p><strong>Get-CsPresencePolicy</strong></p></td>
</tr>
<tr class="even">
<td><p>Criteri conferenza</p></td>
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

