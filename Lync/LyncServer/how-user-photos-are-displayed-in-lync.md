---
title: Come vengono visualizzate le foto degli utenti in Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 6ac13f066c24f66640aee1360caf1d341d604474
ms.sourcegitcommit: 30ed4457d7004ba732372fee11a6f0b1baf48e05
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "40979624"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="http://msdn.microsoft.com/en-us/">

<div data-asp="http://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Come vengono visualizzate le foto degli utenti in Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Argomento Ultima modifica:** 2014-08-25_

**Riepilogo:** Le foto degli utenti visualizzate nel client Lync possono variare a seconda della funzionalità di Lync in uso, ad esempio in una conferenza o in una chat di messaggistica istantanea.

Lync 2010 ha introdotto la possibilità di includere una foto con il proprio profilo Lync che viene visualizzato ad altri utenti di Lync. È anche possibile scegliere se visualizzare o meno le foto per i contatti nel client Lync. In Lync 2013 è supportato il supporto per le foto ad alta risoluzione per gli utenti. Questo argomento descrive il modo in cui il client Lync viene visualizzato e visualizza le foto degli utenti, in cui sono archiviate le immagini, le limitazioni per ogni origine di immagine e la modalità di utilizzo delle foto degli utenti da servizi Lync diversi.

<div>

## <a name="planning-considerations"></a>Considerazioni sulla pianificazione

Quando si pianifica di implementare il supporto per le foto degli utenti, tenere presente quanto segue.

  - Il supporto per le foto degli utenti ad alta definizione richiede che la cassetta postale dell'utente si trovi in Exchange 2013 e che l'account utente di Lync sia in Lync 2013 pool.

  - Le foto degli utenti ad alta definizione sono supportate solo in un ambiente in cui vengono usati sia Lync Server 2013 che Exchange 2013.

  - Gli utenti con cassette postali in Exchange 2010 utilizzeranno sempre l'attributo **ThumbNailPhoto** di servizi di dominio Active Directory come origine per la propria foto utente.

  - Una foto utente archiviata come attributo **ThumbNailPhoto** da servizi di dominio Active Directory non verrà visualizzata per i contatti esterni/federati.

  - Se le foto per i contatti utente sono archiviate in servizi di dominio Active Directory, il file di immagine usato è limitato a 96 × 96 pixel e non supera le dimensioni del file di 100 KB.

  - Se si perde la connettività tra Lync Server ed Exchange Server, viene visualizzato il **ThumbNailPhoto** a bassa risoluzione dell'utente da servizi di dominio Active Directory e solo agli utenti interni.

  - Le foto degli utenti ad alta risoluzione vengono visualizzate nelle riunioni di Lync 2013 quando un altoparlante attivo non è abilitato per il video. Inoltre, spostando il mouse sulla foto in anteprima nella raccolta verrà visualizzata la foto ad alta risoluzione.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Foto degli utenti in Lync 2010

Nel client Lync 2010 è possibile scegliere tra due opzioni per visualizzare una foto per il profilo, l' **immagine aziendale predefinita** e la visualizzazione **dell'immagine da un indirizzo Web**.

<div>

## <a name="default-corporate-picture"></a>Immagine aziendale predefinita

Quando si sceglie l'opzione **immagine aziendale predefinita** , Lync riceve la foto visualizzata da servizi di dominio Active Directory. L'immagine usata è l'immagine definita come valore per l'attributo **ThumbNailPhoto** in servizi di dominio Active Directory. Si tratta dello stesso file usato da Exchange per visualizzare le immagini in Outlook.

Le considerazioni relative all'uso di immagini da servizi di dominio Active Directory includono le seguenti:

  - Sono supportate solo le immagini con dimensioni fino a 96 pixel per 96 pixel. Le dimensioni del file per l'immagine sono limitate a 100 KB.

  - Per impostazione predefinita, gli utenti possono modificare l'immagine usata per l'attributo **ThumbNailPhoto** , anche se non direttamente tramite client Lync. Puoi disabilitare questa operazione tramite servizi di dominio Active Directory.

  - Le immagini archiviate in servizi di dominio Active Directory non vengono visualizzate ai contatti esterni all'organizzazione, anche se sono contatti federati.

  - Nelle organizzazioni di grandi dimensioni, l'archiviazione e il recupero delle immagini per un numero elevato di utenti possono influire sulle dimensioni e sulle prestazioni del database dei servizi di dominio Active Directory.

  - Le dimensioni limitate delle immagini e le dimensioni dei file indicano che possono essere usate solo immagini a bassa risoluzione.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Modalità di gestione delle foto degli utenti in servizi di dominio Active Directory

L'utente non può modificare l'immagine usata nel profilo dei servizi di dominio Active Directory direttamente tramite il client Lync 2010. Possono usare una delle opzioni seguenti per eseguire questa operazione, se disponibile:

  - ****   Gli utenti di SharePoint Server possono caricare una foto in "sito personale" in un server di SharePoint e quindi [configurare la sincronizzazione del profilo in SharePoint](http://go.microsoft.com/fwlink/p/?linkid=507466) per sincronizzare la foto con l'attributo **ThumbNailPhoto** in servizi di dominio Active Directory.

  - **Foto archiviate in URL**   accessibili pubblicamente gli utenti possono configurare la propria foto utente specificando un URL accessibile pubblicamente per l'immagine che vuole usare. L'immagine deve essere pubblicamente accessibile senza una password. L'immagine archiviata presso l'indirizzo Web specificato viene trasferita ad altri utenti tramite la categoria della scheda contatto nelle informazioni sulla presenza. Quando il client Lync deve visualizzare una foto utente, recupera l'immagine dall'indirizzo Web specificato.

  - **I cmdlet di Exchange 2010 per gli amministratori di Windows PowerShell**   possono eseguire il cmdlet [Import-RecipientDataProperty](http://go.microsoft.com/fwlink/p/?linkid=507468) in Exchange 2010 Management Shell in per gestire l'attributo **ThumbNailPhoto** . Quando le immagini vengono importate con i cmdlet di Exchange 2010, la dimensione del file è limitata a 10 KB.

  - **Strumenti di terze parti**   gli utenti possono caricare solo la propria foto per l'attributo **ThumbNailPhoto** .

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Visualizzare un'immagine da un indirizzo Web

Quando si sceglie l'opzione **Mostra un'immagine da un indirizzo Web** , Lync ottiene l'immagine all'indirizzo immesso e la Visualizza per la foto dell'utente in Lync.

Le considerazioni relative all'uso di immagini da un indirizzo Web includono le seguenti:

  - I limiti delle dimensioni dei file sono determinati dall'attributo **MaxPhotoSizeKB** nel criterio client, definito con il cmdlet [New-CsClientPolicy](http://go.microsoft.com/fwlink/p/?linkid=507463) . Il limite di dimensione predefinito è di 30 KB. Il valore massimo è 100 KB. Non esiste alcuna restrizione per la risoluzione dell'immagine, ma se si prova a usare un file di immagine che supera il limite di dimensioni non verrà scaricato nei client Lync. Puoi impostare il valore su 0 per disabilitare l'uso di tutte le foto degli utenti in Lync.

  - Le foto degli utenti da un indirizzo Web possono essere visualizzate da contatti federati esterni.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Gestione della foto dell'utente con i cmdlet dei criteri client

In Lync Server 2010 le impostazioni dei criteri client sono configurate con i cmdlet CsClientPolicy. Le impostazioni dei criteri configurate vengono inviate ai client tramite il provisioning in banda. I due parametri dei cmdlet CsClientPolicy che determinano l'esperienza di foto utente sono **DisplayPhoto** e **MaxPhotoSizeKB**. Il parametro di provisioning in banda corrispondente per **DisplayPhoto** e **MaxPhotoSizeKB** è denominato **fotoutilizzo**. I valori per il parametro di **fotoutilizzo** vengono inviati ai client tramite la **provisionGroup** **EndpointConfiguration** . Per altre informazioni, vedere [Panoramica dei criteri e delle impostazioni client](http://go.microsoft.com/fwlink/?linkid=507470) .

Il valore del parametro **DisplayPhoto** determina l'origine dell'immagine della foto dell'utente. I valori supportati sono inclusi nella tabella seguente.


<table>
<colgroup>
<col style="width: 33%" />
<col style="width: 33%" />
<col style="width: 33%" />
</colgroup>
<thead>
<tr class="header">
<th>Valore del parametro DisplayPhoto</th>
<th>Origine immagini</th>
<th>Impostazioni client di Lync 2010</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>Nophoto</p></td>
<td><p>nessuno</p></td>
<td><p><strong>Non mostrare l'immagine personale</strong></p></td>
</tr>
<tr class="even">
<td><p>PhotoFromADOnly</p></td>
<td><p>Active Directory</p></td>
<td><p><strong>Immagine aziendale predefinita</strong></p></td>
</tr>
<tr class="odd">
<td><p>AllPhotos</p></td>
<td><p>Indirizzo Web</p></td>
<td><p><strong>Visualizzare un'immagine da un indirizzo Web</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Come il client Lync 2010 ottiene le foto

In Lync 2010 le foto degli utenti vengono gestite dal server tramite il servizio Rubrica. Il client Lync riceve le foto degli utenti prima di eseguire una query sul servizio query Web della Rubrica (ABWQ) nel server, esposto tramite il servizio Web di espansione della lista di distribuzione. Il client riceve il file di immagine e lo copia nella cache dell'utente per evitare di scaricare l'immagine ogni volta che deve essere visualizzata. I valori di attributo restituiti dalla query vengono archiviati anche nella voce del servizio rubrica memorizzata nella cache per l'utente. Il servizio Rubrica Elimina tutte le immagini memorizzate nella cache ogni 24 ore, quindi può richiedere fino a 24 ore affinché le nuove immagini degli utenti vengano aggiornate nella cache del server. Puoi forzare un aggiornamento alla cache usando il cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .

Le foto utente incluse nello stato presenza hanno anche un valore hash associato che il client Lync USA per determinare se è disponibile un'immagine più recente. Il client riceve automaticamente una notifica delle modifiche apportate al file di immagine usato nello stato presenza.

<div class=" ">


> [!NOTE]  
> Poiché le foto non sono archiviate nel database GalContacts. DB, il download delle foto utente non dipende dall'impostazione <STRONG>AddressBookAvailability</STRONG> nel criterio client (<A href="http://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).



</div>

La query al servizio ABWQ include gli attributi seguenti:

  - **Fotohash**   il valore hash dei dati di foto binari e viene usato per determinare se la foto corrente è cambiata.

  - **PhotoRelPath**   il percorso relativo al file di immagine archiviato nel server.

  - **Ridimensionare le dimensioni**   del file di immagine in byte.

  - **TimeStamp**   la data e l'ora in cui il file di immagine è stato scaricato l'ultima volta dal server e copiato nella cache del client.

Dopo aver recuperato il file di immagine, il client Lync 2010 confronta i valori degli attributi restituiti dalla query in base ai valori degli attributi ricevuti dal client da provisioning in banda per verificare se sono diversi. Se i valori sono diversi, il client recupera il file di immagine dell'utente connesso con una richiesta HTTP GET.

Inoltre, il client controlla con il server ogni 24 ore dall'ora in cui è stata creata la versione memorizzata nella cache del file di immagine per confrontare il valore dell'attributo **fotohash** nel server con il valore sul client. Se i valori sono diversi, il client sa che il file di immagine è cambiato. Per ottenere il file di immagine aggiornato, il client esegue di nuovo una query sul servizio ABWQ per aggiornare il file di immagine nella cache del client con il file di immagine nel server, che reimposta anche il **timestamp** nel file nella cache del client.

Di seguito è riportato un esempio di risposta a una query al servizio ABWQ:
```xml
    <Attribute>
              <Name>PhotoRelPath</Name>
              <Value>efa6096aed2746cb9ab2037f7dbdde9d.f2eeeb5946db54a7aa607ecd3ae09d
              95.photo</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
              <Name>PhotoHash</Name>
              <Value>f2eeeb5946db54a7aa607ecd3ae09d95</Value>
              <Values xmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays" i:nil="true" />
    </Attribute>
    <Attribute>
         <Name>PhotoSize</Name>
         <Value>4620</Value>
         <Valuesxmlns:d6p1="http://schemas.microsoft.com/2003/10/Serialization/Arrays"
    i:nil="true" />
    </Attribute>
```

</div>

</div>

<div>

## <a name="user-photos-in-lync-2013"></a>Foto degli utenti in Lync 2013

Lync 2013 ha introdotto il supporto per le immagini ad alta risoluzione per le foto degli utenti. Lync 2013 include anche il supporto per l'archiviazione delle foto degli utenti nella cassetta postale dell'utente in Exchange 2013, che rimuove le limitazioni relative alla risoluzione e alle dimensioni delle immagini presenti in Lync 2010. Le foto degli utenti in Lync 2013 possono contenere fino a 648 pixel per 648 pixel con una dimensione di file fino a 20 MB. Le foto ad alta risoluzione in Lync 2013 devono trovarsi nella cassetta postale dell'utente in Exchange 2013 e sono supportate solo con il client Lync 2013. Questa integrazione con Exchange sfrutta il nuovo Framework di autorizzazione incluso nelle versioni di 2013 di Lync, Exchange e SharePoint denominato OAuth.

Se Exchange 2013 non viene usato nella distribuzione, il supporto per le foto degli utenti è uguale a quello di Lync 2010. Tuttavia, le opzioni utente per scegliere la foto da usare sono diverse nel client Lync 2013. Nel client Lync 2013 gli utenti possono selezionare **Nascondi immagine** o **Mostra immagine personale**. L'opzione **Mostra un'immagine da un sito Web** non è disponibile per impostazione predefinita, ma può essere abilitata assegnando un criterio client.

<div>

## <a name="hide-my-picture"></a>Nascondere l'immagine personale

Le impostazioni per le foto degli utenti si trovano nella finestra di dialogo **Opzioni** in Lync 2013. Quando si sceglie **Nascondi immagine personale**, non viene visualizzata alcuna foto utente nel client Lync, ma la foto viene ancora visualizzata nella scheda contatto e all'esterno di Lync.

</div>

<div>

## <a name="show-my-picture"></a>Mostrare l'immagine personale

Quando si sceglie l'opzione **Mostra immagine personale** , la foto utente viene visualizzata nel client Lync e ad altri utenti nelle conversazioni di Lync. L'immagine usata è quella archiviata in servizi di dominio Active Directory.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Visualizzare un'immagine da un sito Web

L'opzione **Mostra immagine da un sito Web** diventa disponibile in Lync 2013 dopo che è stato impostato un criterio client per abilitarlo. La versione client deve essere più recente di 15.0.4535.1002, che viene installata con gli [aggiornamenti cumulativi di Lync: 2013 novembre](http://go.microsoft.com/fwlink/p/?linkid=509908). Per visualizzare le modifiche apportate al client, è possibile che gli utenti debbano disconnettersi e quindi eseguire di nuovo il backup.

Puoi impostare i criteri client per consentire di **visualizzare l'immagine da un'impostazione del sito Web** eseguendo il criterio [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) in Lync Server Management Shell. I cmdlet di esempio seguenti illustrano come impostare i criteri globalmente per tutti gli utenti della distribuzione:

   ```powershell
    $pe=New-CsClientPolicyEntry -Name EnablePresencePhotoOptions -Value True
   ```

   ```powershell
    $po=Get-CsClientPolicy -Identity Global
   ```

   ```powershell
    $po.PolicyEntry.Add($pe)
   ```

   ```powershell
    Set-CsClientPolicy -Instance $po
   ```


Quando un'immagine viene caricata nella cassetta postale dell'utente, Exchange crea automaticamente una versione di risoluzione inferiore dell'immagine che può essere usata nelle applicazioni client. La foto utente viene aggiornata anche in servizi di dominio Active Directory.

<div class=" ">


> [!NOTE]  
> Quando un file di immagine viene aggiornato in servizi di dominio Active Directory, viene creata e usata un'immagine pixel di 48 x 48 per thumbnailPhoto in servizi di dominio Active Directory. Qualsiasi immagine esistente viene sostituita. Quindi, se è stata aggiunta un'immagine di 96 x 96 a servizi di dominio Active Directory, verrà sovrascritta con la nuova immagine di 48 x 48. Questa operazione è importante solo per gli utenti dell'ambiente che usano i client Lync 2010, in quanto tali client otterranno le foto degli utenti da servizi di dominio Active Directory. È possibile importare immagini in pixel di 96 x 96 in sostituzione di quelle create da servizi di dominio Active Directory se sono presenti client Lync 2010 nell'organizzazione.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Supporto per le foto degli utenti in Lync 2013

In Lync 2013 sono supportate tre risoluzioni di immagine per le foto degli utenti, come descritto nella tabella seguente. L'immagine usata è determinata dall'impostazione del criterio client assegnata agli utenti di Lync. Per altre informazioni, vedere "gestione della foto dell'utente con i cmdlet dei criteri client" in questo argomento.


<table>
<colgroup>
<col style="width: 50%" />
<col style="width: 50%" />
</colgroup>
<thead>
<tr class="header">
<th>Risoluzione immagine (pixel)</th>
<th>Applicazione</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><p>48 x 48</p></td>
<td><p>Usato se non è selezionata un'immagine con risoluzione superiore</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Usato in Outlook Web App e Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Usato nel client desktop Lync 2013 e in Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


Qualsiasi utente con una cassetta postale abilitata in Exchange 2013 può caricare un'immagine diversa, incluse le foto ad alta risoluzione, tramite Outlook Web Access o le opzioni client di Lync 2013. Le impostazioni consigliate per le immagini usate includono:

  - **Risoluzione immagine 648**   per 648 pixel

  - **Profondità di colore**   a 24 bit

  - **Dimensioni del file di immagine**   fino a 20 MB

  - **Formato file JPEG**   

Un'immagine JPEG a 24 bit tipica di 648 pixel per 648 pixel ha una dimensione di file di circa 240 KB, quindi è necessario 1 MB di spazio di archiviazione per ogni 4 foto utente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

