---
title: Rilasciare certificati AV e OAuth in Skype for Business Server con-roll in Set-CsCertificate
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.collection: IT_Skype16
ms.assetid: 22dec3cc-4b6b-4df2-b269-5b35df4731a7
description: 'Riepilogo: certificati per la fase AV e OAuth per Skype for Business Server.'
ms.openlocfilehash: 530e8f603d2c5be368df37354c3974e2b5abeb5a
ms.sourcegitcommit: e64c50818cac37f3d6f0f96d0d4ff0f4bba24aef
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/06/2020
ms.locfileid: "41818728"
---
# <a name="stage-av-and-oauth-certificates-in-skype-for-business-server-using--roll-in-set-cscertificate"></a>Rilasciare certificati AV e OAuth in Skype for Business Server con-roll in Set-CsCertificate
 
**Riepilogo:** I certificati di fase AV e OAuth per Skype for Business Server.
  
Le comunicazioni audio/video (A/V) sono un componente chiave di Skype for Business Server. Le caratteristiche come la condivisione delle applicazioni e le conferenze audio e video si basano sui certificati assegnati al servizio a/V Edge, in particolare il servizio di autenticazione A/V.
  
> [!IMPORTANT]
> Questa nuova funzionalità è progettata per l'utilizzo per il servizio A/V Edge e per il certificato OAuthTokenIssuer. È possibile effettuare il provisioning di altri tipi di certificato insieme al servizio A/V Edge e al tipo di certificato OAuth, ma non beneficiano del comportamento di coesistenza che verrà eseguito dal certificato del servizio A/V Edge.
  
I cmdlet di PowerShell per Skype for Business Server Management Shell usati per gestire i certificati di Skype for Business Server si riferiscono al certificato del servizio A/V Edge come tipo di certificato AudioVideoAuthentication e al certificato OAuthServer come typeOAuthTokenIssuer. Per il resto di questo argomento e per identificare in modo univoco i certificati, questi verranno definiti dallo stesso tipo di identificatore, AudioVideoAuthentication andOAuthTokenIssuer.
  
Il servizio di autenticazione A/V è responsabile per il rilascio di token usati dai client e da altri utenti A/V. I token vengono generati dagli attributi del certificato e quando il certificato scade, la perdita di connessione e il requisito di ricongiungersi con un nuovo token generato dal nuovo certificato si tradurrà. Una nuova funzionalità di Skype for Business Server allevierà questo problema: la possibilità di organizzare un nuovo certificato prima della scadenza e consentendo a entrambi i certificati di continuare a funzionare per un periodo di tempo. Questa funzionalità Usa le funzionalità aggiornate nel cmdlet Set-CsCertificate di Skype for Business Server Management Shell. Il nuovo parametro-roll, con il parametro-EffectiveDate esistente, inserisce il nuovo certificato AudioVideoAuthentication nell'archivio certificati. Il certificato AudioVideoAuthentication precedente rimarrà ancora valido per i token emessi da convalidare. A partire dall'immissione del nuovo certificato AudioVideoAuthentication, si verificherà la serie di eventi seguente:
  
> [!TIP]
> Usando i cmdlet di Skype for Business Server Management Shell per la gestione dei certificati è possibile richiedere certificati distinti e distinti per ogni scopo nell'Edge Server. L'uso della procedura guidata certificati nella distribuzione guidata di Skype for Business Server consente di creare certificati, ma in genere è il tipo **predefinito** che tutti i certificati usano per il server perimetrale in un singolo certificato. La procedura consigliata se si vuole usare la caratteristica del certificato rotante consiste nel disaccoppiare il certificato AudioVideoAuthentication dagli altri scopi del certificato. È possibile eseguire il provisioning e la fase di un certificato del tipo predefinito, ma solo la parte AudioVideoAuthentication del certificato combinato trarrà vantaggio dalla gestione temporanea. Un utente coinvolto (ad esempio) una conversazione di messaggistica istantanea quando il certificato scade deve disconnettersi e accedere nuovamente per usare il nuovo certificato associato al servizio Access Edge. Si verificherà un comportamento simile per un utente coinvolto in una conferenza Web tramite il servizio Web Conferencing Edge. Il certificato OAuthTokenIssuer è un tipo specifico condiviso in tutti i server. Si crea e si gestisce il certificato in un'unica posizione e il certificato viene archiviato in Central Management store per tutti gli altri server.
  
È necessario ulteriore dettaglio per comprendere appieno le opzioni e i requisiti quando si usa il cmdlet Set-CsCertificate e usarlo per eseguire la fase dei certificati prima della scadenza del certificato corrente. Il parametro-Roll è importante, ma in sostanza un unico scopo. Se lo si definisce come parametro, si sta dicendo a Set-CsCertificate che verranno fornite informazioni sul certificato che sarà influenzato da tipo definito (ad esempio AudioVideoAuthentication e OAuthTokenIssuer), quando il certificato diventerà efficacia definita da-EffectiveDate.
  
 **-Roll**: il parametro-Roll è obbligatorio e contiene le dipendenze che devono essere fornite insieme. Parametri obbligatori per definire completamente quali certificati saranno interessati e come verranno applicati:
  
 **-EffectiveDate**: il parametro-EffectiveDate definisce quando il nuovo certificato diventerà coattivo con il certificato corrente. Il EffectiveDate può essere vicino all'ora di scadenza del certificato corrente oppure può essere un periodo di tempo più lungo. Una EffectiveDate minima consigliata per il certificato AudioVideoAuthentication sarebbe di 8 ore, ovvero la durata del token predefinita per i token del servizio Edge AV emessi con il certificato AudioVideoAuthentication.
  
Quando si verificano i certificati di OAuthTokenIssuer, esistono requisiti diversi per il tempo di anticipo prima che il certificato diventi effettivo. Il tempo minimo che deve avere il certificato OAuthTokenIssuer per il tempo di consegna è 24 ore prima della data di scadenza del certificato corrente. Il tempo di esecuzione esteso per la coesistenza è dovuto ad altri ruoli del server che dipendono dal certificato OAuthTokenIssuer (ad esempio, server Exchange) che ha un tempo di conservazione più lungo per l'autenticazione e la chiave di crittografia create da un certificato materiali.
  
 **-Identificazione personale**: l'identificazione personale è un attributo del certificato univoco per tale certificato. Il parametro-identificazione personale viene usato per identificare il certificato che verrà influenzato dalle azioni del cmdlet Set-CsCertificate.
  
 **-Type**: il parametro-Type può accettare un singolo tipo di utilizzo del certificato o un elenco separato da virgole dei tipi di utilizzo del certificato. I tipi di certificato sono quelli che identificano il cmdlet e al server lo scopo del certificato. Ad esempio, digitare AudioVideoAuthentication per l'uso da parte del servizio A/V Edge e del servizio di autenticazione AV. Se si decide di eseguire la fase e il provisioning di certificati di un tipo diverso contemporaneamente, è necessario considerare il tempo di anticipo effettivo minimo richiesto per i certificati. Ad esempio, è necessario organizzare i certificati di tipo AudioVideoAuthentication e OAuthTokenIssuer. Il valore minimo di EffectiveDate deve essere maggiore dei due certificati, in questo caso OAuthTokenIssuer, che ha un tempo di anticipo minimo di 24 ore. Se non si vuole eseguire la fase di esecuzione del certificato AudioVideoAuthentication con un tempo di anticipo di 24 ore, eseguire la fase separatamente con un EffectiveDate più per le proprie esigenze.
  
### <a name="to-update-or-renew-an-av-edge-service-certificate-with-a--roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato A/V Edge service con i parametri a-roll e-EffectiveDate

1. Accedere al computer locale come membro del gruppo Administrators.
    
2. Richiedere un rinnovo o un nuovo certificato AudioVideoAuthentication con la chiave privata esportabile per il certificato esistente nel servizio A/V Edge.
    
3. Importare il nuovo certificato AudioVideoAuthentication nel server perimetrale e in tutti gli altri Edge Server nel pool (se è stato distribuito un pool).
    
4. Configurare il certificato importato con il cmdlet Set-CsCertificate e usare il parametro-roll con il parametro-EffectiveDate. La data effettiva deve essere definita come scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno durata del token (per impostazione predefinita otto ore). In questo modo, il certificato deve essere impostato su attivo ed è la stringa \<\>-EFFECTIVEDATE: "7/22/2015 6:00:00 AM". 
    
    > [!IMPORTANT]
    > Per un pool di Edge, è necessario disporre di tutti i certificati AudioVideoAuthentication distribuiti e provisionati in base alla data e all'ora definiti dal parametro-EffectiveDate del primo certificato distribuito per evitare possibili interruzioni di comunicazioni a/V a causa del vecchio certificato che scade prima che tutti i client e i token di consumo siano stati rinnovati con il nuovo certificato. 
  
    Il comando Set-CsCertificate con il parametro-roll e-EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          <thumb print of new certificate> -Roll -EffectiveDate <date and time
          for certificate to become active>
   ```

    Comando Set-CsCertificate di esempio:
    
   ```PowerShell
   Set-CsCertificate -Type AudioVideoAuthentication -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/22/2015
          6:00:00 AM"
   ```

    > [!IMPORTANT]
    > EffectiveDate deve essere formattato in base alle impostazioni dell'area geografica e della lingua del server. Nell'esempio vengono usate le impostazioni della lingua e dell'area inglese degli Stati Uniti 
  
Per comprendere ulteriormente il processo che Set-CsCertificate,-roll e-EffectiveDate USA per creare un nuovo certificato per il rilascio di nuovi token AudioVideoAuthentication mentre si usa ancora un certificato esistente per convalidare AudioVideoAuthentication in uso per i consumatori, una sequenza temporale visiva rappresenta un mezzo efficace per comprendere il processo. Nell'esempio seguente l'amministratore determina che il certificato del servizio A/V Edge è scaduto a 2:00:00 PM su 07/22/2015. Richiede e riceve un nuovo certificato e lo importa in ogni Edge Server nel suo pool. Alle 2 di mattina in 07/22/2015, inizia a eseguire Get-CsCertificate con-roll,-identificazione personale uguale alla stringa di identificazione personale del nuovo certificato e-EffectiveTime impostato su 07/22/2015 6:00:00 AM. Esegue questo comando in ogni server perimetrale.
  
![Uso dei parametri Roll ed EffectiveDate.](../../media/Ops_Certificate_Set_Roll_EffectiveTime_Timeline.jpg)
  
|**Callout**|**Fase**|
|:-----|:-----|
|1  <br/> |Inizio: 7/22/2015 12:00:00 AM  <br/> Il certificato corrente di AudioVideoAuthentication è scaduto a 2:00:00 PM su 7/22/2015. Questo è determinato dall'indicatore di data e ora di scadenza nel certificato. Pianificare la sostituzione del certificato e il rollover per tenere conto di una sovrapposizione di 8 ore (durata token predefinita) prima che il certificato esistente raggiunga il tempo di scadenza. In questo esempio viene usato il tempo di anticipo di 2:00:00 AM per consentire all'amministratore un tempo sufficiente per inserire e eseguire il provisioning dei nuovi certificati prima del tempo effettivo 6:00:00.  <br/> |
|2  <br/> |7/22/2015 2:00:00 AM-7/22/2015 5:59:59 AM  <br/> Impostare i certificati su Edge Server con tempo effettivo di 6:00:00 AM (4 ore di anticipo per questo esempio, ma può essere più lungo) tramite Set-CsCertificate- \<tipo di utilizzo\> del certificato \<-identificazione personale del\> nuovo certificato-Roll \<-EffectiveDate DateTime stringa del tempo effettivo per il nuovo certificato\>  <br/> |
|3  <br/> |7/22/2015 6:00 AM-7/22/2015 2:00 PM  <br/> Per convalidare i token, il nuovo certificato viene provato per primo e, se il nuovo certificato non riesce a convalidare il token, viene provato il vecchio certificato. Questo processo viene usato per tutti i token durante il periodo di sovrapposizione di 8 ore (durata del token predefinito).  <br/> |
|4  <br/> |Fine: 7/22/2015 2:00:01 PM  <br/> Il vecchio certificato è scaduto e il nuovo certificato ha assunto il controllo. Il vecchio certificato può essere rimosso in modo sicuro con il tipo \<\> di utilizzo del certificato Remove-CsCertificate-Type-Previous  <br/> |
   
Quando viene raggiunto il tempo effettivo (7/22/2015 6:00:00 AM), tutti i nuovi token vengono emessi dal nuovo certificato. Quando si convalidano i token, i token verranno prima convalidati in base al nuovo certificato. Se la convalida non riesce, viene provato il vecchio certificato. Il processo per provare il nuovo e il ritorno al vecchio certificato continuerà fino all'ora di scadenza del vecchio certificato. Dopo la scadenza del certificato precedente (7/22/2015 2:00:00 PM), i token verranno convalidati solo dal nuovo certificato. Il vecchio certificato può essere rimosso in modo sicuro usando il cmdlet Remove-CsCertificate con il parametro-Previous.

```PowerShell
Remove-CsCertificate -Type AudioVideoAuthentication -Previous
```

### <a name="to-update-or-renew-an-oauthtokenissuer-certificate-with-a--roll-and--effectivedate-parameters"></a>Per aggiornare o rinnovare un certificato OAuthTokenIssuer con i parametri a-roll e-EffectiveDate

1. Accedere al computer locale come membro del gruppo Administrators.
    
2. Richiedere un rinnovo o un nuovo certificato OAuthTokenIssuer con la chiave privata esportabile per il certificato esistente nel server front-end.
    
3. Importare il nuovo certificato OAuthTokenIssuer in un server front-end nel pool (se è stato distribuito un pool). Il certificato OAuthTokenIssuer viene replicato globalmente e deve essere aggiornato e rinnovato solo in qualsiasi server della distribuzione. Il server front-end viene usato come esempio.
    
4. Configurare il certificato importato con il cmdlet Set-CsCertificate e usare il parametro-roll con il parametro-EffectiveDate. La data effettiva deve essere definita come il periodo di scadenza del certificato corrente (14:00:00 o 2:00:00 PM) meno un minimo di 24 ore. 
    
    Il comando Set-CsCertificate con il parametro-roll e-EffectiveTime:
    
   ```PowerShell
   Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint <thumb
          print of new certificate> -Roll -EffectiveDate <date and time for
          certificate to become active> -identity Global 
   ```

Comando Set-CsCertificate di esempio:
    
  ```PowerShell
  Set-CsCertificate -Type OAuthTokenIssuer -Thumbprint
          "B142918E463981A76503828BB1278391B716280987B" -Roll -EffectiveDate "7/21/2015
          1:00:00 PM" 
  ```

> [!IMPORTANT]
> EffectiveDate deve essere formattato in base alle impostazioni dell'area geografica e della lingua del server. Nell'esempio vengono usate le impostazioni della lingua e dell'area inglese degli Stati Uniti 
  
Quando viene raggiunto il tempo effettivo (7/21/2015 1:00:00 AM), tutti i nuovi token vengono emessi dal nuovo certificato. Quando si convalidano i token, i token verranno prima convalidati in base al nuovo certificato. Se la convalida non riesce, viene provato il vecchio certificato. Il processo per provare il nuovo e il ritorno al vecchio certificato continuerà fino all'ora di scadenza del vecchio certificato. Dopo la scadenza del certificato precedente (7/22/2015 2:00:00 PM), i token verranno convalidati solo dal nuovo certificato. Il vecchio certificato può essere rimosso in modo sicuro usando il cmdlet Remove-CsCertificate con il parametro-Previous.
```PowerShell
Remove-CsCertificate -Type OAuthTokenIssuer -Previous 
```

## <a name="see-also"></a>Vedere anche

[Gestire l'autenticazione da server a server (OAuth) e le applicazioni partner in Skype for Business Server](server-to-server-and-partner-applications.md)

[Set-CsCertificate](https://docs.microsoft.com/powershell/module/skype/set-cscertificate?view=skype-ps)
  
[Remove-CsCertificate](https://docs.microsoft.com/powershell/module/skype/remove-cscertificate?view=skype-ps)
