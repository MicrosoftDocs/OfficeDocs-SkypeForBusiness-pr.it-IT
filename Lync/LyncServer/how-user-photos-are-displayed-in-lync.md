---
title: Modalità di visualizzazione delle foto degli utenti in Lync
ms.reviewer: ''
ms.author: kenwith
author: kenwith
f1.keywords:
- NOCSH
TOCTitle: How user photos are displayed in Lync
ms:assetid: b44a364d-a1d2-4d45-b27a-b5f77775e233
ms:mtpsurl: https://technet.microsoft.com/en-us/library/Dn783119(v=OCS.15)
ms:contentKeyID: 62835297
ms.date: 08/27/2014
manager: serdars
mtps_version: v=OCS.15
ms.openlocfilehash: 2b2c64d0a147457eb50a778d7909b3ccfbf8fecc
ms.sourcegitcommit: 831d141dfc5a49dd764cb296b73b63e5a9f8e599
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 02/21/2020
ms.locfileid: "42180359"
---
<div data-xmlns="http://www.w3.org/1999/xhtml">

<div class="topic" data-xmlns="http://www.w3.org/1999/xhtml" data-msxsl="urn:schemas-microsoft-com:xslt" data-cs="https://msdn.microsoft.com/">

<div data-asp="https://msdn2.microsoft.com/asp">

# <a name="how-user-photos-are-displayed-in-lync"></a>Modalità di visualizzazione delle foto degli utenti in Lync

</div>

<div id="mainSection">

<div id="mainBody">

<span> </span>

_**Ultimo argomento modificato:** 2014-08-25_

**Riepilogo:** Le foto degli utenti visualizzate nel client Lync possono variare a seconda della caratteristica di Lync in uso, ad esempio in una conferenza o in una chat di messaggistica istantanea.

Lync 2010 è stata introdotta la possibilità di includere una foto con il profilo di Lync visualizzato ad altri utenti di Lync. È anche possibile scegliere se visualizzare o meno le foto per i contatti nel client Lync. In Lync 2013, supporto per le foto ad alta risoluzione per gli utenti. In questo argomento viene descritto il modo in cui il client Lync ottiene e visualizza le foto degli utenti, in cui vengono archiviate le immagini, le limitazioni per ogni origine di immagine e la modalità di utilizzo delle foto degli utenti da diversi servizi Lync.

<div>

## <a name="planning-considerations"></a>Considerazioni sulla pianificazione

Quando si pianifica l'implementazione del supporto per le foto degli utenti, è necessario tenere presente quanto segue.

  - Il supporto per le foto degli utenti ad alta definizione richiede che la cassetta postale dell'utente sia presente in Exchange 2013 e che l'account utente di Lync sia incluso nel pool Lync 2013.

  - Le foto degli utenti ad alta definizione sono supportate solo in un ambiente in cui vengono utilizzati sia Lync Server 2013 che Exchange 2013.

  - Gli utenti con cassette postali su Exchange 2010 utilizzeranno sempre l'attributo **ThumbNailPhoto** di ad DS come origine per la foto dell'utente.

  - Una foto utente memorizzata come attributo **ThumbNailPhoto** da servizi di dominio Active Directory non verrà visualizzata per i contatti esterni/federati.

  - Se le foto dei contatti utente sono archiviate in servizi di dominio Active Directory, il file di immagine utilizzato è limitato a 96 × 96 pixel e non supera le dimensioni del file di 100 KB.

  - Se la connettività tra Lync Server e Exchange Server viene persa, l' **ThumbNailPhoto** a bassa risoluzione dell'utente da servizi di dominio Active Directory verrà visualizzato e solo per gli utenti interni.

  - Le foto degli utenti ad alta risoluzione vengono visualizzate nelle riunioni di Lync 2013 quando un altoparlante attivo non dispone di video abilitato. Inoltre, se si sposta il puntatore del mouse sulla foto di anteprima nella raccolta, viene visualizzata la foto ad alta risoluzione.

</div>

<div>

## <a name="user-photos-in-lync-2010"></a>Foto degli utenti in Lync 2010

Nel client Lync 2010, è possibile scegliere tra due opzioni per visualizzare una foto per il profilo, l' **immagine aziendale predefinita** e la visualizzazione **dell'immagine da un indirizzo Web**.

<div>

## <a name="default-corporate-picture"></a>Immagine aziendale predefinita

Quando si sceglie l'opzione **immagine aziendale predefinita** , Lync ottiene la foto visualizzata per l'utente da servizi di dominio Active Directory. L'immagine utilizzata è l'immagine definita come valore per l'attributo **ThumbNailPhoto** in servizi di dominio Active Directory. Questo è lo stesso file utilizzato da Exchange per visualizzare le immagini in Outlook.

Di seguito sono riportate le considerazioni relative all'utilizzo di immagini da servizi di dominio Active Directory:

  - Sono supportate solo le immagini con dimensioni fino a 96 pixel per 96 pixel. Le dimensioni dei file per l'immagine sono limitate a 100 KB.

  - Per impostazione predefinita, gli utenti sono in grado di modificare l'immagine utilizzata per l'attributo **ThumbNailPhoto** , anche se non direttamente tramite il client Lync. È possibile disabilitarlo tramite servizi di dominio Active Directory.

  - Le immagini archiviate in servizi di dominio Active Directory non vengono visualizzate ai contatti esterni all'organizzazione, anche se sono contatti federati.

  - Nelle organizzazioni di grandi dimensioni, l'archiviazione e il recupero delle immagini per un numero elevato di utenti possono influire sulle prestazioni e le dimensioni del database di servizi di dominio Active Directory.

  - Le dimensioni limitate delle immagini e le dimensioni dei file indicano che è possibile utilizzare solo immagini a bassa risoluzione.

<div>

## <a name="how-users-manage-their-user-photos-in-active-directory-domain-services"></a>Come gli utenti gestiscono le proprie foto utente in servizi di dominio Active Directory

L'utente non può modificare l'immagine utilizzata nel proprio profilo servizi di dominio Active Directory direttamente tramite il client Lync 2010. Se disponibile, è possibile utilizzare una delle seguenti opzioni:

  - ****   Gli utenti di SharePoint Server possono caricare una foto in "sito personale" in un server di SharePoint e quindi [configurare la sincronizzazione dei profili in SharePoint](https://go.microsoft.com/fwlink/p/?linkid=507466) per sincronizzare la foto con l'attributo **ThumbNailPhoto** in servizi di dominio Active Directory.

  - **Foto archiviate su URL**   accessibili pubblicamente gli utenti possono configurare la foto utente specificando un URL accessibile pubblicamente per l'immagine che si desidera utilizzare. L'immagine deve essere accessibile pubblicamente senza una password. L'immagine memorizzata nell'indirizzo Web specificato viene trasferita ad altri utenti tramite la categoria di schede contatto nelle informazioni sulla presenza. Quando il client Lync deve visualizzare una foto utente, l'immagine viene recuperata dall'indirizzo Web specificato.

  - **I cmdlet di Exchange 2010 per gli amministratori di Windows PowerShell**   possono eseguire il cmdlet [Import-RecipientDataProperty](https://go.microsoft.com/fwlink/p/?linkid=507468) in Exchange 2010 Management Shell in per gestire l'attributo **ThumbNailPhoto** . Quando le immagini vengono importate con i cmdlet di Exchange 2010, la dimensione del file è limitata a 10 KB.

  - **Strumenti di terze parti**   gli utenti possono caricare solo la propria foto per l'attributo **ThumbNailPhoto** .

</div>

</div>

<div>

## <a name="show-a-picture-from-a-web-address"></a>Mostra l'immagine da un indirizzo Web

Quando si sceglie l'opzione **Mostra un'immagine da un indirizzo Web** , Lync ottiene l'immagine all'indirizzo immesso e la Visualizza per la foto dell'utente in Lync.

Di seguito sono riportate le considerazioni relative all'utilizzo di immagini da un indirizzo Web:

  - I limiti relativi alle dimensioni dei file sono determinati dall'attributo **MaxPhotoSizeKB** nel criterio client, definito con il cmdlet [New-CsClientPolicy](https://go.microsoft.com/fwlink/p/?linkid=507463) . Il limite di dimensione predefinito è 30 KB. Il valore massimo è 100 KB. Non vi sono restrizioni sulla risoluzione dell'immagine, ma se si tenta di utilizzare un file di immagine che supera il limite di dimensione, non verrà scaricato nei client Lync. È possibile impostare il valore su 0 per disabilitare l'utilizzo di tutte le foto degli utenti in Lync.

  - Le foto degli utenti provenienti da un indirizzo Web possono essere visualizzate da contatti federati esterni.

</div>

<div>

## <a name="managing-users-photo-with-client-policy-cmdlets"></a>Gestione delle foto degli utenti con i cmdlet dei criteri client

In Lync Server 2010, le impostazioni dei criteri client sono configurate con i cmdlet di CsClientPolicy. Le impostazioni dei criteri configurate vengono inviate ai client tramite il provisioning in-band. I due parametri dei cmdlet di CsClientPolicy che determinano l'esperienza della foto utente sono **DisplayPhoto** e **MaxPhotoSizeKB**. Il parametro di provisioning di tipo in-band corrispondente per **DisplayPhoto** e **MaxPhotoSizeKB** è denominato **fotoutilizzo**. I valori per il parametro **DataUsage** sono Send to clients through the **EndpointConfiguration** **provisionGroup**. Per ulteriori informazioni, vedere [Overview of client Policies and Settings](https://go.microsoft.com/fwlink/?linkid=507470) .

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
<th>Origine immagine</th>
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
<td><p><strong>Mostra l'immagine da un indirizzo Web</strong></p></td>
</tr>
</tbody>
</table>


</div>

<div>

## <a name="how-lync-2010-client-gets-photos"></a>Come viene ottenuta la foto dal client Lync 2010

In Lync 2010, le foto degli utenti vengono gestite sul server dal servizio Rubrica. Il client Lync ottiene le foto degli utenti eseguendo prima una query sul servizio query Web della Rubrica (ABWQ) nel server, esposto tramite il servizio Web di espansione della lista di distribuzione. Il client riceve il file di immagine e quindi lo copia nella cache dell'utente per evitare di scaricare l'immagine ogni volta che deve essere visualizzata. I valori degli attributi restituiti dalla query vengono archiviati anche nella voce del servizio rubrica memorizzata nella cache per l'utente. Il servizio Rubrica Elimina tutte le immagini memorizzate nella cache ogni 24 ore, il che significa che possono essere necessarie fino a 24 ore prima che le nuove immagini degli utenti vengano aggiornate nella cache sul server. È possibile forzare un aggiornamento alla cache utilizzando il cmdlet [Update-CsAddressBook](https://docs.microsoft.com/powershell/module/skype/Update-CsAddressBook) .

Le foto degli utenti incluse nello stato di presenza dispongono anche di un valore hash associato utilizzato dal client Lync per determinare se è disponibile un'immagine più recente. Il client riceve automaticamente una notifica delle modifiche apportate al file di immagine utilizzato nello stato di presenza.

<div class=" ">


> [!NOTE]  
> Poiché le foto non sono archiviate nel database di GalContacts. DB, il download delle foto utente non dipende dall'impostazione <STRONG>AddressBookAvailability</STRONG> nel criterio client (<A href="https://go.microsoft.com/fwlink/p/?linkid=507508">Set-CsClientPolicy</A>).



</div>

La query per il servizio ABWQ include gli attributi seguenti:

  - **Fotohash**   il valore hash dei dati delle foto binarie e viene utilizzato per determinare se la foto corrente è stata modificata.

  - **PhotoRelPath**   il percorso relativo al file di immagine memorizzato nel server.

  - **Ridimensionare le dimensioni**   del file di immagine, in byte.

  - **TimeStamp**   la data e l'ora in cui è stato scaricato l'ultimo file di immagine dal server e copiato nella cache client.

Successivamente, dopo aver recuperato il file di immagine, Lync 2010 client confronta i valori degli attributi restituiti dalla query in base ai valori di attributo ricevuti dal client dal provisioning di tipo in-band per verificare se sono diversi. Se i valori sono diversi, il client recupererà il file di immagine dell'utente connesso con una richiesta HTTP GET.

Inoltre, il client verifica con il server ogni 24 ore dal momento in cui è stata creata la versione memorizzata nella cache del file di immagine per confrontare il valore dell'attributo **fotohash** sul server con il valore sul client. Se i valori sono diversi, il client sa che il file di immagine è stato modificato. Per ottenere il file di immagine aggiornato, il client esegue di nuovo una query sul servizio ABWQ per aggiornare il file di immagine nella cache del client con il file di immagine nel server, che reimposta anche il **timestamp** sul file nella cache client.

Di seguito è riportato un esempio di risposta a una query per il servizio ABWQ:
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

Lync 2013 ha introdotto il supporto per le immagini ad alta risoluzione per le foto degli utenti. Lync 2013 include anche il supporto per l'archiviazione delle foto degli utenti nella cassetta postale dell'utente su Exchange 2013, che rimuove la risoluzione dell'immagine e le limitazioni relative alle dimensioni presenti in Lync 2010. Le foto degli utenti in Lync 2013 possono essere fino a 648 pixel per 648 pixel con dimensioni di un file fino a 20 MB. Le foto ad alta risoluzione in Lync 2013 devono essere situate nella cassetta postale dell'utente su Exchange 2013 e sono supportate solo con il client Lync 2013. Questa integrazione con Exchange si avvale del nuovo Framework di autorizzazione incluso nelle versioni 2013 di Lync, Exchange e SharePoint denominato OAuth.

Se Exchange 2013 non viene utilizzato nella distribuzione, il supporto per le foto degli utenti è lo stesso di Lync 2010. Tuttavia, le opzioni utente per scegliere la foto da utilizzare sono diverse nel client Lync 2013. Nel client Lync 2013, gli utenti possono scegliere di **nascondere la foto** o di **visualizzare l'immagine**. L'opzione **Mostra un'immagine da un sito Web** non è disponibile per impostazione predefinita, ma può essere abilitata assegnando un criterio client.

<div>

## <a name="hide-my-picture"></a>Nascondi immagine

Le impostazioni per le foto degli utenti sono disponibili nella finestra di dialogo **Opzioni** in Lync 2013. Quando si sceglie **Nascondi immagine**, non viene visualizzata alcuna foto utente nel client Lync, ma la foto è ancora visualizzata nella scheda contatto e all'esterno di Lync.

</div>

<div>

## <a name="show-my-picture"></a>Mostra immagine personale

Quando si sceglie l'opzione **Mostra immagine personale** , la foto utente viene visualizzata nel client Lync e ad altri utenti nelle conversazioni di Lync. L'immagine utilizzata è quella memorizzata in servizi di dominio Active Directory.

</div>

<div>

## <a name="show-a-picture-from-a-website"></a>Visualizzazione di un'immagine da un sito Web

L'opzione **Mostra immagine da un sito Web** diventa disponibile in Lync 2013 dopo che è stato impostato un criterio client per abilitarlo. La versione client deve essere più recente di 15.0.4535.1002, che viene installata con gli [aggiornamenti cumulativi di Lync: novembre 2013](https://go.microsoft.com/fwlink/p/?linkid=509908). Gli utenti potrebbero dover disconnettersi e quindi eseguire nuovamente l'accesso per visualizzare le modifiche apportate al client.

È possibile impostare il criterio client in modo da consentire la **visualizzazione di un'immagine da un'impostazione del sito Web** eseguendo il criterio [Set-CsClientPolicy](https://docs.microsoft.com/powershell/module/skype/Set-CsClientPolicy) in Lync Server Management Shell. Nei cmdlet di esempio riportati di seguito viene illustrato come impostare il criterio a livello globale per tutti gli utenti nella distribuzione:

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


Quando un'immagine viene caricata nella cassetta postale dell'utente, Exchange crea automaticamente una versione di risoluzione più bassa dell'immagine che può essere utilizzata nelle applicazioni client. La foto dell'utente viene aggiornata anche in servizi di dominio Active Directory.

<div class=" ">


> [!NOTE]  
> Quando un file di immagine viene aggiornato in servizi di dominio Active Directory, viene creata e utilizzata un'immagine di 48 x 48 pixel per il thumbnailPhoto in servizi di dominio Active Directory. Qualsiasi immagine esistente viene sostituita. Pertanto, se è stata aggiunta un'immagine di 96 x 96 a servizi di dominio Active Directory, verrà sovrascritta con la nuova immagine 48 x 48. Questo è importante solo se si dispone di utenti nell'ambiente che utilizzano client Lync 2010, in quanto tali client otterranno foto utente da servizi di dominio Active Directory. Se si dispone di client Lync 2010 nell'organizzazione, è possibile importare immagini da 96 x 96 pixel per sostituire quelle create da servizi di dominio Active Directory.



</div>

</div>

<div>

## <a name="user-photo-support-in-lync-2013"></a>Supporto per le foto degli utenti in Lync 2013

In Lync 2013, sono supportate tre risoluzioni immagine per le foto degli utenti, come descritto nella tabella seguente. L'immagine utilizzata è determinata dall'impostazione del criterio client assegnata agli utenti di Lync. Per ulteriori informazioni, vedere la sezione relativa alla gestione delle foto degli utenti con i cmdlet per i criteri client.


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
<td><p>Viene utilizzata se non è selezionata alcuna immagine con risoluzione superiore</p></td>
</tr>
<tr class="even">
<td><p>96 x 96</p></td>
<td><p>Utilizzato in Outlook Web App e Outlook 2013</p></td>
</tr>
<tr class="odd">
<td><p>648 x 648</p></td>
<td><p>Utilizzato in Lync 2013 client desktop e Lync 2013 Web App</p></td>
</tr>
</tbody>
</table>


Qualsiasi utente con una cassetta postale abilitata in Exchange 2013 può caricare un'immagine diversa, incluse le foto ad alta risoluzione, tramite le opzioni client di Outlook Web Access o Lync 2013. Le impostazioni consigliate per le immagini utilizzate sono le seguenti:

  - **Risoluzione immagine 648**   per 648 pixel

  - **Profondità di colore**   a 24 bit

  - **Dimensione del file di immagine**   fino a 20 MB

  - **Formato**   JPEG di file

Un'immagine JPEG a 24 bit tipica di 648 pixel per 648 pixel ha dimensioni di un file di circa 240 KB, quindi è necessario un MB di spazio di archiviazione per ogni 4 foto utente.

</div>

</div>

</div>

<span> </span>

</div>

</div>

</div>

