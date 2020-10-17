---
title: 'Lync Server 2013: configurazione di Lync Server in un ambiente cross-premise'
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
ms.openlocfilehash: 6f6399185e045afb56231550abc33ab514db0d04
ms.sourcegitcommit: 4d6bf5c58b2c553dc1df8375ede4a9cb9eaadff2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/16/2020
ms.locfileid: "48517383"
---
# <a name="configuring-microsoft-lync-server-2013-in-a-cross-premises-environment"></a>Configurazione di Microsoft Lync Server 2013 in un ambiente cross-premise

<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">



</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2017-02-21_

In una configurazione cross-premise, alcuni utenti sono ospitati in un'installazione locale di Microsoft Lync Server 2013 mentre altri utenti sono ospitati nella versione Microsoft 365 o Office 365 di Lync Server. Per configurare l'autenticazione da server a server in un ambiente cross-premise, è innanzitutto necessario configurare l'installazione locale di Lync Server 2013 in modo che consideri attendibile il server di autorizzazione Microsoft 365. È possibile eseguire il passaggio iniziale di questo processo eseguendo il seguente script di Lync Server Management Shell:

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

Tenere a mente che il nome dell'area di autenticazione di un tenant è solitamente diverso da quello dell'organizzazione. Quasi mai il nome dell'area di autenticazione corrisponde a quello dell'ID del tenant. Per questo motivo, la prima riga dello script è utilizzata per restituire il valore della proprietà TenantId del tenant specificato (in questo caso, fabrikam.com) e per poi assegnare il nome alla variabile $TenantId:

    $TenantID = (Get-CsTenant -DisplayName "Fabrikam.com").TenantId

Dopo aver completato lo script, è necessario configurare una relazione di trust tra Lync Server 2013 e il server di autorizzazione, nonché una seconda relazione di trust tra Exchange 2013 e il server di autorizzazione. È possibile farlo soltanto attraverso i cmdlet di Microsoft Online Services.

<div>


> [!NOTE]  
> Se i cmdlet di Microsoft Online Services non sono installati, è necessario eseguire due operazioni prima di procedere. Per prima cosa, scaricare e installare la versione a 64 bit di Microsoft Online Services Sign-in Assistant. Al termine dell'installazione, scaricare e installare la versione 64 bit del modulo dei Microsoft Online Services per Windows PowerShell. Informazioni dettagliate per l'installazione e l'utilizzo del modulo dei Microsoft Online Services sono disponibili nel sito Web Microsoft 365 o Office 365. Queste istruzioni illustrano inoltre come configurare il servizio Single Sign-on, la Federazione e la sincronizzazione tra Microsoft 365 o Office 36 e Active Directory.<BR>Se i cmdlet non sono stati installati, lo script avrà esito negativo perché il cmdlet Get-CsTenant non sarà disponibile.



</div>

Dopo aver configurato Microsoft 365 e dopo aver creato le entità di servizio di Microsoft 365 o Office 365 per Lync Server 2013 ed Exchange 2013, sarà necessario registrare le credenziali con queste entità di servizio. Per farlo, è necessario ottenere un certificato base64 X.509 salvato come file .CER. Questo certificato verrà quindi applicato alle entità di servizio Microsoft 365 o Office 365.

Dopo aver ottenuto il certificato X. 509, avviare il modulo dei Microsoft Online Services (fare clic sul pulsante **Start**, scegliere **tutti i programmi**, **Microsoft Online Services**e quindi fare clic su **modulo dei Microsoft Online Services per Windows PowerShell**). Dopo l'apertura del modulo servizi, digitare il comando seguente per importare il modulo Microsoft online di Windows PowerShell contenente i cmdlet che possono essere utilizzati per gestire le entità di servizio:

    Import-Module MSOnlineExtended

Quando il modulo è stato importato, digitare il comando seguente e quindi premere INVIO per connettersi a Microsoft 365:

    Connect-MsolService

A questo punto, viene visualizzata una finestra di dialogo delle credenziali. Immettere il nome utente e la password di Microsoft 365 o Office 365 nella finestra di dialogo e quindi fare clic su OK.

Non appena si è connessi a Microsoft 365, è possibile eseguire il comando seguente per restituire le informazioni sulle entità di servizio:

    Get-MsolServicePrincipal

Si dovrebbero ottenere informazioni simili alle seguenti, per tutti i nomi del servizio principale:

    ExtensionData        : System.Runtime.Serialization.ExtensionDataObject
    AccountEnabled       : True
    Addresses            : {}
    AppPrincipalId       : 00000004-0000-0ff1-ce00-000000000000
    DisplayName          : Microsoft Lync Server
    ObjectId             : aada5fbd-c0ae-442a-8c0b-36fec40602e2
    ServicePrincipalName : LyncServer/litwareinc.com
    TrustedForDelegation : True

Il passaggio successivo consiste nell'importazione, codifica e assegnazione del certificato X.509. Per importare e codificare il certificato, utilizzare i seguenti comandi di Windows PowerShell, assicurandosi di specificare il percorso completo del file. File CER quando si chiama il metodo Import:

    $certificate = New-Object System.Security.Cryptography.X509Certificates.X509Certificate
    $certificate.Import("C:\Certificates\Office365.cer")
    $binaryValue = $certificate.GetRawCertData()
    $credentialsValue = [System.Convert]::ToBase64String($binaryValue)

Dopo che il certificato è stato importato e codificato, è possibile assegnare il certificato alle entità di servizio Microsoft 365. A tale scopo, utilizzare prima la Get-MsolServicePrincipal per recuperare il valore della proprietà AppPrincipalId per le entità dei servizi Lync Server e Microsoft Exchange. il valore della proprietà AppPrincipalId verrà utilizzato per identificare l'entità di servizio a cui è assegnato il certificato. Con il valore della proprietà AppPrincipalId per Lync Server 2013 in mano, utilizzare il seguente comando per assegnare il certificato alla versione Microsoft 365 di Lync Server (le proprietà StartDate e EndDate devono corrispondere al periodo di validità del certificato):

    New-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -Type Asymmetric -Usage Verify -Value $credentialsValue -StartDate 6/1/2012 -EndDate 5/31/2013

È quindi necessario ripetere il comando, stavolta utilizzando il valore della proprietà AppPrincipalId per Exchange 2013.

Se successivamente si ha bisogno di eliminare il certificato, è possibile farlo recuperando il KeyId per il certificato:

    Get-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000

Il comando restituisce dati simili ai seguenti:

    Type      : Asymmetric
    Value     : 
    KeyId     : bc2795f3-2387-4543-a95d-f92c85c7a1b0
    StartDate : 6/1/2012 8:00:00 AM
    EndDate   : 5/31/2013 8:00:00 AM
    Usage     : Verify

È possibile eliminare il certificato utilizzando un comando simile al seguente:

    Remove-MsolServicePrincipalCredential -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -KeyId bc2795f3-2387-4543-a95d-f92c85c7a1b0

Oltre all'assegnazione di un certificato, è necessario configurare anche l'entità servizio Microsoft 365 per Exchange Online aggiungendo il nome dell'entità server per la versione locale di Lync Server 2013. A tale scopo, è possibile eseguire le quattro righe seguenti in una sessione di PowerShell dei Microsoft Online Services:

    Set-MSOLServicePrincipal -AppPrincipalID 00000002-0000-0ff1-ce00-000000000000 -AccountEnabled $true
    
    $lyncSP = Get-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000
    $lyncSP.ServicePrincipalNames.Add("00000004-0000-0ff1-ce00-000000000000/lync.contoso.com")
    Set-MSOLServicePrincipal -AppPrincipalID 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $lyncSP.ServicePrincipalNames

</div>

<span> </span>

</div>

</div>

</div>

