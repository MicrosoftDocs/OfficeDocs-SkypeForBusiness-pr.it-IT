---
title: 'Lync Server 2013: configurazione di Lync Server in un ambiente cross-locale'
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
f1.keywords:
- NOCSH
TOCTitle: Configuring Microsoft Lync Server 2013 in a cross-premises environment
ms:assetid: 700639ec-5264-4449-a8a6-d7386fad8719
ms:mtpsurl: https://technet.microsoft.com/en-us/library/JJ204990(v=OCS.15)
ms:contentKeyID: 48184449
ms.date: 02/21/2017
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 02696b85921e2f408b7a7ec5531b0596aaef49ba
ms.sourcegitcommit: b693d5923d6240cbb865241a5750963423a4b33e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/04/2020
ms.locfileid: "41755950"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>Configurazione di Microsoft Lync Server 2013 in un ambiente tra più locali

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2017-02-21_

In una configurazione interlocale, alcuni utenti si trovano in un'installazione locale di Microsoft Lync Server 2013 mentre altri utenti si trovano nella versione di Office 365 di Lync Server. Per configurare l'autenticazione da server a server in un ambiente Multilocale, è prima necessario configurare l'installazione locale di Lync Server 2013 per considerare attendibile il server di autorizzazione di Office 365. Il passaggio iniziale di questo processo può essere eseguito eseguendo il seguente script di Lync Server Management Shell:

    $TenantID = (Get-CsTenant -Filter {DisplayName -eq "Fabrikam.com"}).TenantId
    
    $sts = Get-CsOAuthServer microsoft.sts -ErrorAction SilentlyContinue
            
       if ($sts -eq $null)
          {
             New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
          }
       else
          {
             if ($sts.MetadataUrl -ne  "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1")
                {
                   Remove-CsOAuthServer microsoft.sts
                   New-CsOAuthServer microsoft.sts -MetadataUrl "https://accounts.accesscontrol.windows.net/$TenantId/metadata/json/1"
                }
            }
    
    $exch = Get-CsPartnerApplication microsoft.exchange -ErrorAction SilentlyContinue
            
    if ($exch -eq $null)
       {
          New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer
        }
    else
        {
           if ($exch.ApplicationIdentifier -ne "00000002-0000-0ff1-ce00-000000000000")
              {
                 Remove-CsPartnerApplication microsoft.exchange
                 New-CsPartnerApplication -Identity microsoft.exchange -ApplicationIdentifier 00000002-0000-0ff1-ce00-000000000000 -ApplicationTrustLevel Full -UseOAuthServer 
              }
           else
              {
                 Set-CsPartnerApplication -Identity microsoft.exchange -ApplicationTrustLevel Full -UseOAuthServer
              }
       }
    
    Set-CsOAuthConfiguration -ServiceName 00000004-0000-0ff1-ce00-000000000000

Tieni presente che il nome dell'area di autenticazione per un tenant è in genere diverso rispetto al nome dell'organizzazione; il nome Realm è infatti quasi sempre uguale all'ID tenant. Per questo motivo, la prima riga nello script viene usata per restituire il valore della proprietà ID tenant per il tenant specificato (in questo caso fabrikam.com) e quindi assegnare il nome alla variabile $TenantId:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

Al termine dello script, è necessario configurare una relazione di trust tra Lync Server 2013 e il server di autorizzazione e una seconda relazione di trust tra Exchange 2013 e il server di autorizzazione. Questa operazione può essere eseguita solo usando i cmdlet dei Microsoft Online Services.

<div>


> [!NOTE]  
> Se non sono stati installati i cmdlet dei Microsoft Online Services, è necessario eseguire due operazioni prima di procedere. Prima di tutto, scaricare e installare la versione a 64 bit dell'assistente per l'accesso ai Microsoft Online Services. Al termine dell'installazione, scaricare e installare la versione a 64 bit del modulo Microsoft Online Services per Windows PowerShell. Informazioni dettagliate per l'installazione e l'uso del modulo Microsoft Online Services si trovano nel sito Web di Office 365. Queste istruzioni spiegano anche come configurare Single Sign-on, Federation e la sincronizzazione tra Office 365 e Active Directory.<BR>Se non sono stati installati questi cmdlet, lo script non riuscirà perché il cmdlet Get-CsTenant non sarà disponibile.



</div>

Dopo aver configurato Office 365 e dopo aver creato le entità di servizio di Office 365 per Lync Server 2013 ed Exchange 2013, sarà necessario registrare le credenziali con queste entità di servizio. Per eseguire questa operazione, devi prima ottenere un X. 509 Base64 salvato come. File CER. Questo certificato verrà quindi applicato alle entità di servizio di Office 365.

Dopo aver ottenuto il certificato X. 509, avviare il modulo Microsoft Online Services (fare clic sul pulsante **Start**, scegliere **tutti i programmi**, fare clic su **Microsoft Online Services**e quindi su **modulo Microsoft Online Services per Windows PowerShell**). Dopo l'apertura del modulo servizi, digitare quanto segue per importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che possono essere usati per gestire le entità di servizio:

    Import-Module MSOnlineExtended

Quando il modulo è stato importato, digitare il comando seguente e quindi premere INVIO per connettersi a Office 365:

    Connect-MsolService

Dopo aver premuto INVIO, verrà visualizzata una finestra di dialogo credenziali. Immettere il nome utente e la password di Office 365 nella finestra di dialogo e quindi fare clic su OK.

Non appena si è connessi a Office 365, è possibile eseguire il comando seguente per restituire informazioni sulle entità di servizio:

    Get-MsolServicePrincipal

È consigliabile recuperare informazioni simili a quelle per tutte le entità di servizio:

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

Il passaggio successivo consiste nell'importare, codificare e assegnare il certificato X. 509. Per importare e codificare il certificato, usare i comandi di Windows PowerShell seguenti, in modo da specificare il percorso completo del file. File CER quando si chiama il metodo di importazione:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Dopo aver importato e codificato il certificato, è possibile assegnare il certificato alle entità di servizio di Office 365. A questo scopo, USA prima di tutto Get-MsolServicePrincipal viene per recuperare il valore della proprietà AppPrincipalId sia per il server Lync che per le entità dei servizi di Microsoft Exchange. il valore della proprietà AppPrincipalId verrà usato per identificare l'entità del servizio a cui è stato assegnato il certificato. Con il valore della proprietà AppPrincipalId per Lync Server 2013 in mano, usare il comando seguente per assegnare il certificato alla versione di Office 365 di Lync Server (le proprietà StartDate ed EndDate devono corrispondere al periodo di validità del certificato):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

Devi quindi ripetere il comando, questa volta usando il valore della proprietà AppPrincipalId per Exchange 2013.

Se in seguito è necessario eliminare il certificato, è possibile eseguire prima di tutto il recupero di KeyId per il certificato:

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

Il comando restituirà dati come questo:

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

È quindi possibile eliminare il certificato usando un comando simile al seguente:

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

Oltre ad assegnare un certificato, è necessario configurare anche l'entità di servizio di Office 365 per Exchange Online aggiungendo il nome dell'entità server per la versione locale di Lync Server 2013. Questa operazione può essere eseguita eseguendo le quattro righe seguenti in una sessione di PowerShell di Microsoft Online Services:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

