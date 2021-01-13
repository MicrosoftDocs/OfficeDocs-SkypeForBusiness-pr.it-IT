---
title: Stage AV e OAuth Certificates in Skype for Business Server using-roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Sintesi: Stage AV e OAuth Certificates per Skype for Business Server.'
ms.openlocfilehash: a2586e9ebda1bae1605fd6033681b469e6731b8c
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49806556"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Stage AV e OAuth Certificates in Skype for Business Server using-roll in Set-CsCertificate
 
**Riepilogo:** In stage AV e OAuth Certificates per Skype for Business Server.
  
Le comunicazioni audio/video (A/V) sono un componente chiave di Skype for Business Server. Funzionalità quali la condivisione di applicazioni e le conferenze audio e video si basano sui certificati assegnati al servizio A/V Edge, in particolare il servizio di autenticazione A/V.
  
> [!IMPORTANT]
> Questa nuova funzionalità è progettata per funzionare con il servizio A/V Edge e il certificato OAuthTokenIssuer. È possibile eseguire il provisioning di altri tipi di certificato insieme al servizio A/V Edge e al tipo di certificato OAuth, ma non beneficiare del comportamento di coesistenza del certificato del servizio A/V Edge.
  
I cmdlet di PowerShell per Skype for Business Server Management Shell utilizzati per gestire i certificati di Skype for Business Server si riferiscono al certificato del servizio A/V Edge come il tipo di certificato AudioVideoAuthentication e il certificato OAuthServer come typeOAuthTokenIssuer. Per il resto di questo argomento e per identificare in modo univoco i certificati, verranno riferiti dallo stesso tipo di identificatore, AudioVideoAuthentication andOAuthTokenIssuer.
  
Il servizio di autenticazione A/V è responsabile dell'emissione di token utilizzati dai client e da altri utenti A/V. I token vengono generati dagli attributi del certificato e, quando il certificato scade, la perdita di connessione e il requisito di riunirsi con un nuovo token generato dal nuovo certificato risultano. Una nuova funzionalità di Skype for Business Server consente di alleviare questo problema: la possibilità di eseguire un nuovo certificato prima della scadenza e di consentire a entrambi i certificati di continuare a funzionare per un determinato periodo di tempo. Questa funzionalità utilizza la funzionalità aggiornata del cmdlet Set-CsCertificate Skype for Business Server Management Shell. Il nuovo parametro-roll, con il parametro-EffectiveDate esistente, inserirà il nuovo certificato AudioVideoAuthentication nell'archivio certificati. Il certificato AudioVideoAuthentication meno recente continuerà a essere convalidato per i token emessi. A partire dalla messa in posizione del nuovo certificato AudioVideoAuthentication, si verificherà la seguente serie di eventi:
  
> [!TIP]
> Utilizzando i cmdlet di Skype for Business Server Management Shell per la gestione dei certificati, è possibile richiedere certificati separati e distinti per ogni scopo nel server perimetrale. L'utilizzo della procedura guidata certificate nella distribuzione guidata di Skype for Business Server consente di creare certificati, ma in genere è il tipo **predefinito** per il quale tutti i certificati vengono utilizzati per il server perimetrale su un singolo certificato. Se si intende utilizzare la funzionalità di certificati in sequenza, la procedura consigliata consiste nel disassociare il certificato AudioVideoAuthentication dagli scopi degli altri certificati. È possibile effettuare il provisioning e gestire temporaneamente un certificato di tipo predefinito, ma solo la parte AudioVideoAuthentication del certificato combinato sfrutterà i vantaggi della gestione temporanea. Un utente coinvolto (ad esempio) una conversazione di messaggistica istantanea quando il certificato scade avrà bisogno di disconnettersi e accedere nuovamente per utilizzare il nuovo certificato associato al servizio Access Edge. Si verificherà un comportamento analogo per un utente coinvolto in una conferenza Web tramite il servizio Web Conferencing Edge. Il certificato OAuthTokenIssuer è un tipo specifico condiviso in tutti i server. È possibile creare e gestire il certificato in un'unica posizione e il certificato viene archiviato nell'archivio di gestione centrale per tutti gli altri server.
  
Per comprendere appieno le opzioni e i requisiti relativi all'uso del cmdlet Set-CsCertificate e alla gestione temporanea di certificati tramite tale cmdlet prima della scadenza del certificato corrente, sono necessarie altre informazioni. Il parametro-Roll è importante, ma è uno scopo essenzialmente singolo. Se viene definito come parametro, si sta dicendo Set-CsCertificate che verranno fornite informazioni sul certificato che sarà influenzato da tipo definito (ad esempio, AudioVideoAuthentication e OAuthTokenIssuer), quando il certificato diventerà efficace definito da-EffectiveDate.
  
 **-Roll**: il parametro-Roll è obbligatorio e dispone di dipendenze che devono essere fornite insieme. Parametri obbligatori per definire completamente quali certificati saranno interessati e come saranno applicati:
  
 **-EffectiveDate**: il parametro-EffectiveDate definisce quando il nuovo certificato diventerà coattivo con il certificato corrente. Il-EffectiveDate può essere vicino al tempo di scadenza del certificato corrente oppure può essere un periodo di tempo più lungo. Un valore minimo consigliato-EffectiveDate per il certificato AudioVideoAuthentication è di 8 ore, ovvero la durata dei token predefinita per i token del servizio di Edge AV emessi utilizzando il certificato di AudioVideoAuthentication.
  
Quando si gestiscono temporaneamente certificati OAuthTokenIssuer, esistono diversi requisiti per il tempo di anticipo prima che il certificato diventi effettivo. Il tempo di anticipo minimo per il certificato OAuthTokenIssuer è di 24 ore prima dell'ora di scadenza del certificato corrente. Il tempo di anticipo prolungato per la coesistenza è dovuto ad altri ruoli del server dipendenti dal certificato OAuthTokenIssuer (ad esempio Exchange Server) che ha un periodo di memorizzazione più lungo per i materiali di autenticazione e chiave di crittografia creati dal certificato.
  
 **-Thumbprint**: l'identificazione digitale è un attributo univoco per il relativo certificato. Il parametro-identificazione personale viene utilizzato per identificare il certificato che sarà influenzato dalle azioni del cmdlet Set-CsCertificate.
  
 **-Type**: il parametro-Type può accettare un singolo tipo di utilizzo del certificato o un elenco separato da virgole di tipi di utilizzo dei certificati. I tipi di certificati identificato lo scopo del certificato per il cmdlet e il server. Ad esempio, digitare AudioVideoAuthentication è per l'utilizzo da parte del servizio A/V Edge e del servizio di autenticazione AV. Se si decide di gestire temporaneamente ed effettuare il provisioning di certificati di un tipo diverso contemporaneamente, è necessario considerare il più lungo tempo di anticipo effettivo minimo richiesto per i certificati. Ad esempio, è necessario gestire temporaneamente i certificati di tipo AudioVideoAuthentication e OAuthTokenIssuer. Il valore minimo di EffectiveDate deve essere il maggiore dei due certificati, in questo caso il OAuthTokenIssuer, che ha un termine minimo di 24 ore. Se non si desidera gestire temporaneamente il certificato AudioVideoAuthentication con un tempo di anticipo di 24 ore, gestirlo separatamente con un valore di EffectiveDate più adeguato ai requisiti specifici.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato del servizio A/V Edge con i parametri a-roll e-EffectiveDate

1. Accedere al computer locale come membro del gruppo Administrators.
    
2. Richiedere un rinnovo o un nuovo certificato AudioVideoAuthentication con una chiave privata esportabile per il certificato esistente nel servizio A/V Edge.
    
3. Importare il nuovo certificato di AudioVideoAuthentication nel server perimetrale e in tutti gli altri server perimetrali del pool (se è stato distribuito un pool).
    
4. Configurare il certificato importato con il cmdlet Set-CsCertificate e utilizzare il parametro-roll con il parametro-EffectiveDate. La data effettiva deve essere definita come ora di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno la durata del token (otto ore per impostazione predefinita). In questo modo viene indicato che il certificato deve essere impostato su attivo ed è il-EffectiveDate \<string\> : "7/22/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Per un pool di server perimetrali, è necessario disporre di tutti i certificati di AudioVideoAuthentication distribuiti e provisionati in base alla data e all'ora definite dal parametro-EffectiveDate del primo certificato distribuito per evitare possibili interruzioni di comunicazioni a/V a causa del certificato meno recente che scade prima che tutti i client e i token consumer siano stati rinnovati utilizzando il nuovo certificato. 
  
    Il comando Set-CsCertificate con il parametro-roll e-EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Esempio di comando Set-CsCertificate:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate deve essere formattato in modo che corrisponda alle impostazioni della lingua e dell'area del server. Nell'esempio vengono utilizzate le impostazioni di paese e lingua Inglese (Stati Uniti). 
  
Per ulteriori informazioni sul processo di Set-CsCertificate,-roll e-EffectiveDate che consente di eseguire il passaggio di un nuovo certificato per l'emissione di nuovi token AudioVideoAuthentication mentre si utilizza ancora un certificato esistente per convalidare i AudioVideoAuthentication utilizzati dai consumatori, una sequenza temporale visiva rappresenta un mezzo efficace per comprendere il processo. Nell'esempio seguente l'amministratore determina che il certificato del servizio A/V Edge deve scadere alle 2:00:00 PM del 07/22/2015. Richiede e riceve un nuovo certificato e lo importa in ogni server perimetrale del pool. Alle ore 2 del 07/22/2015, inizia a eseguire Get-CsCertificate con-roll,-identificazione personale uguale alla stringa di identificazione personale del nuovo certificato e-EffectiveTime impostato su 07/22/2015 6:00:00 AM. Esegue questo comando in ogni server perimetrale.
  
![Utilizzo dei parametri roll e EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Fase**|
|:-----|:-----|
|1   <br/> |Inizio: 7/22/2015 12:00:00 AM  <br/> Il certificato AudioVideoAuthentication corrente deve scadere alle 2:00:00 del 7/22/2015. Questo è determinato dall'indicatore di data e ora scadenza del certificato. Pianificare la sostituzione del certificato e il rollover per tenere conto di una sovrapposizione di 8 ore (durata token predefinita) prima che il certificato esistente raggiunga il tempo di scadenza. In questo esempio viene utilizzato il tempo di conferimento 2:00:00 AM per consentire all'amministratore di disporre di tempo sufficiente per effettuare il provisioning dei nuovi certificati in anticipo rispetto all'ora 6:00:00 AM effective.  <br/> |
|2   <br/> |7/22/2015 2:00:00 AM-7/22/2015 5:59:59 AM  <br/> Impostare i certificati nei server perimetrali con tempo effettivo di 6:00:00 AM (4 ore di anticipo per questo esempio, ma può essere più lungo) utilizzando Set-CsCertificate-Type \<certificate usage type\> -identificazione personale \<thumbprint of new certificate\> -Roll-EffectiveDate \<datetime string of the effective time for new certificate\>  <br/> |
|3   <br/> |7/22/2015 6:00 AM-7/22/2015 2:00 PM  <br/> Per convalidare i token, il nuovo certificato viene provato per primo e, nel caso in cui il nuovo certificato non riesca a convalidare il token, viene provato il vecchio certificato. Questo processo viene utilizzato per tutti i token durante il periodo di sovrapposizione di 8 ore (durata token predefinita).  <br/> |
|4   <br/> |Fine: 7/22/2015 2:00:01 PM  <br/> Il certificato obsoleto è scaduto e il nuovo certificato è stato rilevato. Il vecchio certificato può essere rimosso in modo sicuro con Remove-CsCertificate-Type \<certificate usage type\> -Previous  <br/> |
   
Quando il tempo effettivo viene raggiunto (7/22/2015 6:00:00), tutti i nuovi token vengono emessi dal nuovo certificato. Durante la convalida dei token, i token verranno prima convalidati rispetto al nuovo certificato. Se la convalida ha esito negativo, viene eseguito il certificato precedente. Il processo di prova del nuovo e del rientro al vecchio certificato continuerà fino alla data di scadenza del certificato precedente. Dopo la scadenza del certificato precedente (7/22/2015 2:00:00 PM), i token verranno convalidati solo dal nuovo certificato. Il vecchio certificato può essere rimosso in modo sicuro usando il cmdlet Remove-CsCertificate con il parametro-Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato di OAuthTokenIssuer con parametri a-roll e-EffectiveDate

1. Accedere al computer locale come membro del gruppo Administrators.
    
2. Richiedere un rinnovo o un nuovo certificato OAuthTokenIssuer con una chiave privata esportabile per il certificato esistente nel front end server.
    
3. Importare il nuovo certificato di OAuthTokenIssuer in un front end server nel pool (se è stato distribuito un pool). Il certificato OAuthTokenIssuer viene replicato globalmente e deve solo essere aggiornato e rinnovato in ogni server nella distribuzione. Il front end server viene utilizzato come esempio.
    
4. Configurare il certificato importato con il cmdlet Set-CsCertificate e utilizzare il parametro-roll con il parametro-EffectiveDate. La data effettiva deve essere definita come ora di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno un minimo di 24 ore. 
    
    Il comando Set-CsCertificate con il parametro-roll e-EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Esempio di comando Set-CsCertificate:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate deve essere formattato in modo che corrisponda alle impostazioni della lingua e dell'area del server. Nell'esempio vengono utilizzate le impostazioni di paese e lingua Inglese (Stati Uniti). 
  
Quando il tempo effettivo viene raggiunto (7/21/2015 1:00:00), tutti i nuovi token vengono emessi dal nuovo certificato. Durante la convalida dei token, i token verranno prima convalidati rispetto al nuovo certificato. Se la convalida ha esito negativo, viene eseguito il certificato precedente. Il processo di prova del nuovo e del rientro al vecchio certificato continuerà fino alla data di scadenza del certificato precedente. Dopo la scadenza del certificato precedente (7/22/2015 2:00:00 PM), i token verranno convalidati solo dal nuovo certificato. Il vecchio certificato può essere rimosso in modo sicuro usando il cmdlet Remove-CsCertificate con il parametro-Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
