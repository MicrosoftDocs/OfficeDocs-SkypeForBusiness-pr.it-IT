---
title: Testare l'installazione di Skype for Business online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 19873b1f-8f7e-4dd8-92f4-2ce11344ed5e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1.keywords:
- NOCSH
ms.custom:
- Setup
description: 'Learn to save time, support calls and increase satisfaction by setting up test accounts and computers, and testing dial-in conferencing, online features such as person-to-person calls, conferencing, and sign in and out. '
ms.openlocfilehash: 378fe1ad980de5c28c9175cf7e1e918b580c257a
ms.sourcegitcommit: 7ebcff93ecbdc064414d7110e182b29371ca4f1f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/06/2021
ms.locfileid: "52239517"
---
# <a name="test-your-skype-for-business-online-installation"></a>Testare l'installazione di Skype for Business online

[!INCLUDE [sfbo-retirement](../../Hub/includes/sfbo-retirement.md)]

[] Per risparmiare tempo, ridurre le chiamate al supporto tecnico e aumentare la soddisfazione dei clienti, esegui una verifica dell'installazione di Skype for Business online prima di configurare il programma per tutti i dipendenti dell'organizzazione.

Ecco quello che occorre:

- Almeno tre account Microsoft 365 o Office 365 (il tuo e almeno altri due).

- Un computer per ogni account di prova. Impostare tali computer con la configurazione tipica dei computer dell'organizzazione.

- Un account supportato da un provider di servizi di audioconferenza per Skype for Business online.

## <a name="what-do-you-want-to-do"></a>Quale operazione si desidera effettuare?

> [Configurare gli account di prova](test-your-skype-for-business-online-installation.md#__toc328126910)
> 
> [Configurare i computer di prova](test-your-skype-for-business-online-installation.md#__toc328126911)
> 
> [Configurare l'audioconferenza](test-your-skype-for-business-online-installation.md#__toc328126912)
> 
> [Verificare i dispositivi e le funzionalità di Skype for Business online](test-your-skype-for-business-online-installation.md#__toc328126913)

## <a name="set-up-test-accounts"></a>Configurare gli account di prova
<a name="__toc328126910"> </a>

1. Passare a **Amministratore Microsoft 365** o Office 365 utenti e gruppi e quindi selezionare Aggiungi e  >   immettere le informazioni   >   ![ ](../images/328ffb57-5f31-430a-b653-4a6b8e76d338.png) necessarie.

2. Al passaggio 4 (Posta elettronica) immettere il proprio indirizzo di posta elettronica. Verrà creato un record che contiene il nome utente e la password per il nuovo utente.

3. Esegui di nuovo i passaggi 1 e 2 fino alla creazione di tutti gli account di prova desiderati. Oltre a quello personale, devi avere almeno altri due account per verificare le funzionalità relative alle riunioni online di Skype for Business online.

## <a name="set-up-test-computers"></a>Configurare computer di prova
<a name="__toc328126911"> </a>

In ogni computer di prova eseguire le seguenti operazioni:

1. Passare alla home page Microsoft 365 o Office 365 e accedere con le credenziali di uno degli account di test.

2. Andare a **Impostazioni**![Impostazioni: aggiornare il profilo, installare il software e connetterlo al cloud](../images/4b83e9cb-c7e4-46c8-b3d1-cfee017123ae.png), quindi fare clic su **Installa il software e connettilo al cloud**.

## <a name="set-up-audio-conferencing"></a>Configurare l’audioconferenza
<a name="__toc328126912"> </a>

Per consentire l'accesso telefonico alle riunioni di Skype for Business online, configura un account con un provider di servizi di audioconferenza. In questo modo puoi ottenere:

- Numeri a tariffa per accesso esterno e numeri verdi, se disponibili.

- Un codice conferenza e un PIN per ogni utente dell'organizzazione che pianifica o conduce le riunioni.

Dopo essere stati configurati per i servizi di audioconferenza, gli utenti riceveranno un messaggio di posta elettronica automatico che contiene i numeri di accesso esterno e il codice della conferenza. Queste informazioni verranno automaticamente aggiunte alle nuove convocazioni di riunione di Skype for Business.

 **Per aggiungere le informazioni relative alle conferenze telefoniche con audio all'account di uno degli utenti di prova**

1. Fare clic **su Utenti audioconferenza**  >  .

2. Fare clic sui nomi degli utenti da configurare per le conferenze telefoniche con accesso esterno, quindi fare clic su **Modifica**![Modifica](../images/2f8948c1-e4f3-4022-b9cd-37fed066056e.png).

3. Selezionare il proprio provider di servizi di audioconferenza, digitare le informazioni richieste e fare clic su **Salva**.

|**Impostazioni delle audioconferenze**|**Descrizione**|
|:-----|:-----|
|**Provider** <br/> |Scegliere il provider di servizi di audioconferenza dall'elenco.  <br/> |
|**Numero a pagamento** (obbligatorio) <br/> |Numeri di telefono ricevuti dal provider di servizi di audioconferenza. Applica ai numeri la formattazione da visualizzare negli inviti alle riunioni di Skype for Business.  <br/> |
|**Numero verde** <br/> |Numeri di telefono ricevuti dal provider di servizi di audioconferenza. Applica ai numeri la formattazione da visualizzare negli inviti alle riunioni di Skype for Business.  <br/> |
|**Passcode** <br/> |Passcode, o codice conferenza, per questo utente.  <br/> |

## <a name="test-skype-for-business-online-features-and-devices"></a>Verificare i dispositivi e le funzionalità di Skype for Business online
<a name="__toc328126913"> </a>

Verifica che le funzionalità principali di Skype for Business online funzionino come previsto.

 **Accesso e disconnessione**

|**Attività**|**Risultato previsto**|
|:-----|:-----|
|[Effettuare l'accesso e disconnettersi da Lync Online](https://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |Viene visualizzata la finestra principale di Skype for Business, con lo stato presenza specificato al momento dell'accesso  <br/> |
|[Effettuare l'accesso e disconnettersi da Lync Online](https://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |Viene visualizzata la schermata di accesso di Skype for Business  <br/> |
|[Effettuare l'accesso e disconnettersi da Lync Online](https://support.office.com/article/1f0fb5f3-102e-4397-a5c4-f878cc0009d6) <br/> |La finestra di Skype for Business viene chiusa e l'icona di Skype for Business non è più visualizzata nell'area di notifica di Windows.  <br/> |

Non riesci ad accedere? Vedi [Come risolvere i problemi di accesso a Skype for Business online](https://support.microsoft.com/kb/2541980).

 **Contatti, presenza e messaggistica istantanea**

|**Attività**|**Risultato previsto**|
|:-----|:-----|
|[Inviare un messaggio istantaneo in Skype for Business](https://support.office.com/article/b3aefb9b-dec8-4be8-a1ee-1eab12144d05) <br/> |Digita del testo nella finestra di conversazione di Skype for Business visualizzata e riceverai una risposta dalla persona contattata.  <br/> |
|[Inviare un messaggio istantaneo in Skype for Business](https://support.office.com/article/b3aefb9b-dec8-4be8-a1ee-1eab12144d05) <br/> |Digita del testo nella finestra di conversazione di Skype for Business visualizzata e chiunque partecipi alla conversazione risponderà.  <br/> |
|[Ricerca di un contatto tramite il nome o il cognome](https://support.office.live.com/article/29fa2061-f679-4e0d-902d-736b67774c8b#BKMK_ContactsFAQ) <br/> |I risultati di ricerca iniziano a comparire non appena si digita qualcosa.  <br/> |
|[Domande frequenti su Lync per Microsoft 365](https://support.office.com/article/29fa2061-f679-4e0d-902d-736b67774c8b.aspx#BKMK_ContactsFAQ) <br/> |Il contatto aggiunto viene visualizzato nel gruppo di contatti scelto.  <br/> |
|[Modificare lo stato presenza in Lync](https://support.office.com/article/ef8998cc-7801-4b62-81ba-9a2c1630f9e5) <br/> |Il nuovo stato presenza viene aggiornato nell'elenco Contatti delle altre persone.  <br/> |
|[Utilizzare la scheda contatto](https://support.office.com/article/19870880-FC90-46B0-9C60-C398518E9FBC) <br/> |La scheda contatto della persona viene visualizzata accanto al nome.  <br/> |

 **Chiamate dirette**

|**Attività**|**Risultato previsto**|
|:-----|:-----|
|[Effettuare e ricevere una chiamata audio Lync](https://support.office.com/article/39342f16-4d16-44de-a806-0b2b566f3886) <br/> |Viene visualizzata la finestra di conversazione e si sente lo squillo della chiamata. La persona chiamata riceve un avviso per il desktop e accetta la chiamata, quindi la finestra di conversazione viene aggiornata quando l'altra persona si connette.  <br/> |
|[Aggiungere audio a una conversazione istantanea di Lync](https://support.office.com/article/21a098b2-63f1-4205-a9aa-532b6a67ea92) <br/> |La chiamata si connette ed è possibile inviare messaggi istantanei e parlare con l'altra persona.  <br/> |
|[Condividere il desktop o un programma in Lync](https://support.office.com/article/33aaa965-eb32-42a9-8a9b-cdfffa364842) <br/> |Il desktop o il programma condiviso è visibile per l'altra persona.  <br/> |

 **Conferenze**

|**Attività**|**Risultato previsto**|
|:-----|:-----|
|[Configurare una riunione Lync](https://support.office.com/article/258f9d20-f06c-49a4-a77f-7f5ac635bb5d) <br/> |Viene inviata una convocazione per la riunione alle persone specificate.  <br/> |
|[Modificare le impostazioni dei partecipanti per le riunioni Lync](https://support.office.com/article/cee2aa78-d878-4a63-ad33-9c249fceced9) <br/> |Variabile a seconda dell'opzione.  <br/> **SUGGERIMENTO:** in **Accessi e relatori** è possibile sperimentare le diverse impostazioni dell'opzione **Persone che evitano la sala di attesa**. <br/> |
|[Partecipazione a una riunione Skype for Business (Lync)](https://support.office.com/article/538716dc-f4f2-48c2-af96-587c62387b87) <br/> |Viene visualizzata la finestra di conversazione e il proprio nome compare nell'elenco dei partecipanti alla riunione dopo la connessione.  <br/> |
|[Attivare o disattivare il microfono in una chiamata o riunione Skype for Business](https://support.office.com/article/47399948-db7f-4ee5-8e61-53a94bb97704) <br/> |L'icona Audio disattivato viene visualizzata accanto al nome di tutte le persone incluse nell'elenco dei partecipanti alla riunione. Solo la voce del relatore è udibile.  <br/> |
|[Presentare diapositive di PowerPoint in una riunione Lync](https://support.office.com/article/3910a2b2-01df-4b97-9451-322b598ede7e) <br/> |La presentazione di PowerPoint viene visualizzata nei computer di tutti i partecipanti nella finestra di condivisione della riunione Skype for Business.  <br/> |
|[Trasferire un file in una riunione di Lync](https://support.office.com/article/f6942910-bc1d-4a48-bf18-385778f08088) <br/> |Dopo il caricamento, tutti nella riunione potranno visualizzare e scaricare l'allegato.  <br/> |

## <a name="related-topics"></a>Argomenti correlati
[Configurare Skype for Business online](set-up-skype-for-business-online.md)

[Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)


