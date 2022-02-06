---
title: Passaggio dei certificati AV e OAuth in Skype for Business Server usando -Roll in Set-CsCertificate
ms.reviewer: null
ms.author: serdars
author: SerdarSoysal
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
  - NOCSH
ms.localizationpriority: medium
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Riepilogo: stage AV and OAuth certificates for Skype for Business Server.'
---

# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Passaggio dei certificati AV e OAuth in Skype for Business Server usando -Roll in Set-CsCertificate
 
**Riepilogo:** Stage AV and OAuth certificates for Skype for Business Server.
  
Le comunicazioni audio/video (A/V) sono un componente chiave della Skype for Business Server. Funzionalità quali la condivisione delle applicazioni e le conferenze audio e video si basano sui certificati assegnati al servizio A/V Edge, in particolare il servizio di autenticazione A/V.
  
> [!IMPORTANT]
> Questa nuova funzionalità è progettata per funzionare per il servizio A/V Edge e il certificato OAuthTokenIssuer. È possibile eseguire il provisioning di altri tipi di certificato insieme al servizio A/V Edge e al tipo di certificato OAuth, ma non trarranno vantaggio dal comportamento di coesistenza del certificato del servizio A/V Edge.
  
I cmdlet di PowerShell di Skype for Business Server Management Shell utilizzati per gestire i certificati Skype for Business Server fanno riferimento al certificato del servizio A/V Edge come tipo di certificato AudioVideoAuthentication e al certificato OAuthServer come typeOAuthTokenIssuer. Per il resto di questo argomento e per identificare in modo univoco i certificati, verranno indicati dallo stesso tipo di identificatore, AudioVideoAuthentication eOAuthTokenIssuer.
  
Il servizio di autenticazione A/V è responsabile dell'emissione di token utilizzati dai client e da altri consumer A/V. I token vengono generati dagli attributi nel certificato e, alla scadenza del certificato, si verifica la perdita di connessione e il requisito di ricongiungersi a un nuovo token generato dal nuovo certificato. Una nuova funzionalità di Skype for Business Server allevierà questo problema: la possibilità di impostare un nuovo certificato prima della scadenza del vecchio e consentire a entrambi i certificati di continuare a funzionare per un periodo di tempo. Questa funzionalità utilizza la funzionalità aggiornata nel cmdlet Set-CsCertificate Skype for Business Server Management Shell. Il nuovo parametro -Roll, con il parametro esistente -EffectiveDate, inserirà il nuovo certificato AudioVideoAuthentication nell'archivio certificati. Il certificato AudioVideoAuthentication precedente rimarrà ancora valido per i token emessi. A partire dall'inserimento del nuovo certificato AudioVideoAuthentication, si verificherà la serie di eventi seguente:
  
> [!TIP]
> Utilizzando i cmdlet Skype for Business Server Management Shell per la gestione dei certificati, è possibile richiedere certificati separati e distinti per ogni scopo nel server perimetrale. L'utilizzo della Configurazione guidata certificati nella Distribuzione guidata di Skype for Business Server consente di creare certificati, ma in genere è del tipo predefinito  che consente di utilizzare tutti i certificati per il server perimetrale in un singolo certificato. Se si intende utilizzare la funzionalità di certificati in sequenza, la procedura consigliata consiste nel disassociare il certificato AudioVideoAuthentication dagli scopi degli altri certificati. È possibile effettuare il provisioning e gestire temporaneamente un certificato di tipo predefinito, ma solo la parte AudioVideoAuthentication del certificato combinato sfrutterà i vantaggi della gestione temporanea. Un utente coinvolto in una conversazione di messaggistica istantanea alla scadenza del certificato dovrà disconnettersi ed eseguire di nuovo l'accesso per utilizzare il nuovo certificato associato al servizio Access Edge. Un comportamento simile si verificherà per un utente coinvolto in una conferenza Web utilizzando il servizio Web Conferencing Edge. Il certificato OAuthTokenIssuer è un tipo specifico condiviso in tutti i server. È possibile creare e gestire il certificato in un'unica posizione e il certificato viene archiviato nell'archivio di gestione centrale per tutti gli altri server.
  
Per comprendere appieno le opzioni e i requisiti relativi all'uso del cmdlet Set-CsCertificate e alla gestione temporanea di certificati tramite tale cmdlet prima della scadenza del certificato corrente, sono necessarie altre informazioni. Il parametro -Roll è importante, ma essenzialmente uno scopo singolo. Se lo definisci come parametro, indicherai a Set-CsCertificate che verranno fornite informazioni sul certificato interessato definito da -Type (ad esempio AudioVideoAuthentication e OAuthTokenIssuer), quando il certificato diventerà effettivo definito da -EffectiveDate.
  
 **-Roll**: il parametro -Roll è obbligatorio e include dipendenze che devono essere fornite insieme a esso. Parametri obbligatori per definire completamente quali certificati saranno interessati e come saranno applicati:
  
 **-EffectiveDate**: il parametro -EffectiveDate definisce quando il nuovo certificato diventerà co-attivo con il certificato corrente. -EffectiveDate può essere vicino alla scadenza del certificato corrente oppure può essere un periodo di tempo più lungo. Un valore minimo consigliato - EffectiveDate per il certificato AudioVideoAuthentication è di 8 ore, ovvero la durata dei token predefinita per i token del servizio AV Edge emessi utilizzando il certificato AudioVideoAuthentication.
  
Quando si gestiscono temporaneamente certificati OAuthTokenIssuer, esistono diversi requisiti per il tempo di anticipo prima che il certificato diventi effettivo. Il tempo di anticipo minimo per il certificato OAuthTokenIssuer è di 24 ore prima dell'ora di scadenza del certificato corrente. Il tempo di anticipo prolungato per la coesistenza è dovuto ad altri ruoli del server dipendenti dal certificato OAuthTokenIssuer (ad esempio Exchange Server) che ha un periodo di memorizzazione più lungo per i materiali di autenticazione e chiave di crittografia creati dal certificato.
  
 **-Thumbprint**: l'identificazione digitale è un attributo univoco per il relativo certificato. Il parametro -Thumbprint viene utilizzato per identificare il certificato interessato dalle azioni del cmdlet Set-CsCertificate.
  
 **-Type**: il parametro -Type può accettare un singolo tipo di utilizzo del certificato o un elenco separato da virgole di tipi di utilizzo del certificato. I tipi di certificati identificato lo scopo del certificato per il cmdlet e il server. Ad esempio, digitare AudioVideoAuthentication per l'utilizzo da parte del servizio A/V Edge e del servizio di autenticazione AV. Se si decide di gestire temporaneamente ed effettuare il provisioning di certificati di un tipo diverso contemporaneamente, è necessario considerare il più lungo tempo di anticipo effettivo minimo richiesto per i certificati. Ad esempio, è necessario gestire temporaneamente i certificati di tipo AudioVideoAuthentication e OAuthTokenIssuer. Il valore minimo -EffectiveDate deve essere il maggiore dei due certificati, in questo caso OAuthTokenIssuer, che ha un lead time minimo di 24 ore. Se non si desidera gestire temporaneamente il certificato AudioVideoAuthentication con un tempo di anticipo di 24 ore, gestirlo separatamente con un valore di EffectiveDate più adeguato ai requisiti specifici.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato del servizio A/V Edge con i parametri -Roll e -EffectiveDate

1. Accedere al computer locale come membro del gruppo Administrators.
    
2. Richiedere un rinnovo o un nuovo certificato AudioVideoAuthentication con chiave privata esportabile per il certificato esistente nel servizio A/V Edge.
    
3. Importare il nuovo certificato AudioVideoAuthentication nel server perimetrale e in tutti gli altri server perimetrali nel pool (se è stato distribuito un pool).
    
4. Configurare il certificato importato con il cmdlet Set-CsCertificate e utilizzare il parametro -Roll con il parametro -EffectiveDate. La data effettiva deve essere definita come ora di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno la durata del token (otto ore per impostazione predefinita). In questo modo il certificato deve essere impostato su attivo ed è -EffectiveDate \<string\>: "22/07/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Per un pool di server perimetrali, è necessario disporre di tutti i certificati AudioVideoAuthentication distribuiti ed emessi in base alla data e all'ora definite dal parametro -EffectiveDate del primo certificato distribuito per evitare possibili interruzioni delle comunicazioni A/V a causa della scadenza del certificato precedente prima che tutti i token client e consumer siano stati rinnovati utilizzando il nuovo certificato. 
  
    Il Set-CsCertificate comando con il parametro -Roll e -EffectiveTime:
    
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
    > La proprietà EffectiveDate deve essere formattata in modo che corrisponda alle impostazioni internazionali e della lingua del server. Nell'esempio vengono utilizzate le impostazioni di paese e lingua Inglese (Stati Uniti). 
  
Per comprendere meglio il processo utilizzato da Set-CsCertificate, -Roll e -EffectiveDate per impostare un nuovo certificato per l'emissione di nuovi token AudioVideoAuthentication pur utilizzando un certificato esistente per convalidare AudioVideoAuthentication in uso dagli utenti, una sequenza temporale visiva è un mezzo efficace per comprendere il processo. Nell'esempio seguente, l'amministratore determina che il certificato del servizio A/V Edge scadrà alle 14.00 del 22/07/2015. Richiede e riceve un nuovo certificato e lo importa in ogni server perimetrale del pool. Alle 2 del 22/07/2015 inizia l'esecuzione di Get-CsCertificate con -Roll, -Thumbprint uguale alla stringa di identificazione personale del nuovo certificato e -EffectiveTime impostato su 22/07/2015 6:00:00 AM. Esegue questo comando in ogni server perimetrale.
  
![Utilizzo dei parametri Roll e EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Fase**|
|:-----|:-----|
|1  <br/> |Inizio: 22/07/2015 12:00:00  <br/> Il certificato AudioVideoAuthentication corrente scadrà alle 14.00 del 22/07/2015. Questo è determinato dall'indicatore di data e ora di scadenza nel certificato. Pianificare la sostituzione e il rollover del certificato per una sovrapposizione di 8 ore (durata token predefinita) prima che il certificato esistente raggiunga la scadenza. Il lead time 2:00:00 am viene utilizzato in questo esempio per consentire all'amministratore un tempo adeguato per collocare ed eseguire il provisioning dei nuovi certificati prima del tempo di validità delle 6:00:00.  <br/> |
|2  <br/> |22/07/2015 2:00:00 - 22/07/2015 05:59:59  <br/> Impostare i certificati nei server perimetrali con tempo effettivo di 6:00:00 (il lead time di 4 ore è per questo esempio, ma può essere più lungo) utilizzando Set-CsCertificate -Type \<certificate usage type\> -Thumbprint \<thumbprint of new certificate\> -Roll -EffectiveDate \<datetime string of the effective time for new certificate\>  <br/> |
|3   <br/> |22/07/2015 06.00 - 22/07/2015 14.00  <br/> Per convalidare i token, il nuovo certificato viene tentato per primo e se il nuovo certificato non riesce a convalidare il token, viene tentato il vecchio certificato. Questo processo viene usato per tutti i token durante il periodo di sovrapposizione di 8 ore (durata dei token predefinita).  <br/> |
|4   <br/> |Fine: 22/07/2015 14:00:01  <br/> Il vecchio certificato è scaduto e il nuovo certificato ha preso il controllo. Il vecchio certificato può essere rimosso in modo sicuro con Remove-CsCertificate -Type \<certificate usage type\> -Previous  <br/> |
   
Quando viene raggiunto il momento di validità (22/07/2015 06.00.00), tutti i nuovi token vengono emessi dal nuovo certificato. Durante la convalida dei token, i token verranno prima convalidati rispetto al nuovo certificato. Se la convalida non riesce, viene tentato il vecchio certificato. Il processo di prova del nuovo certificato e di ripristino del vecchio certificato continuerà fino alla scadenza del vecchio certificato. Una volta scaduto il vecchio certificato (22/07/2015 14.00), i token verranno convalidati solo dal nuovo certificato. Il certificato precedente può essere rimosso in modo sicuro utilizzando il cmdlet Remove-CsCertificate con il parametro -Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato OAuthTokenIssuer con i parametri -Roll e -EffectiveDate

1. Accedere al computer locale come membro del gruppo Administrators.
    
2. Richiedere un rinnovo o un nuovo certificato OAuthTokenIssuer con chiave privata esportabile per il certificato esistente nel Front End Server.
    
3. Importare il nuovo certificato OAuthTokenIssuer in un Front End Server nel pool (se è stato distribuito un pool). Il certificato OAuthTokenIssuer viene replicato globalmente e deve solo essere aggiornato e rinnovato in ogni server nella distribuzione. Il Front End Server viene utilizzato come esempio.
    
4. Configurare il certificato importato con il cmdlet Set-CsCertificate e utilizzare il parametro -Roll con il parametro -EffectiveDate. La data effettiva deve essere definita come ora di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno un minimo di 24 ore. 
    
    Il Set-CsCertificate comando con il parametro -Roll e -EffectiveTime:
    
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
> La proprietà EffectiveDate deve essere formattata in modo che corrisponda alle impostazioni internazionali e della lingua del server. Nell'esempio vengono utilizzate le impostazioni di paese e lingua Inglese (Stati Uniti). 
  
Quando viene raggiunto il momento di validità (21/07/2015 1:00:00), tutti i nuovi token vengono emessi dal nuovo certificato. Durante la convalida dei token, i token verranno prima convalidati rispetto al nuovo certificato. Se la convalida non riesce, viene tentato il vecchio certificato. Il processo di prova del nuovo certificato e di ripristino del vecchio certificato continuerà fino alla scadenza del vecchio certificato. Una volta scaduto il vecchio certificato (22/07/2015 14.00), i token verranno convalidati solo dal nuovo certificato. Il certificato precedente può essere rimosso in modo sicuro utilizzando il cmdlet Remove-CsCertificate con il parametro -Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](/powershell/module/skype/remove-cscertificate?view=skype-ps)