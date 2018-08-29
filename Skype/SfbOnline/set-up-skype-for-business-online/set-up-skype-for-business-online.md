---
title: Configurare Skype for Business online
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
ms.collection: Adm_Skype4B_Online
ms.audience: Admin
appliesto:
- Skype for Business
localization_priority: Normal
f1keywords:
- O365E_SkypeforBusinessON
- O365M_SkypeforBusinessON
- O365P_SkypeforBusinessON
ms.custom:
- Setup
- Alchemy
- LIL_Placement
description: "Informazioni su come impostare il dominio, gli utenti, messaggistica Istantanea e presenza per l'organizzazione per installare Skype per le aziende. Vedere anche come configurare conferenze audio, sistema telefonico e la chiamata dei piani e trasmissione Skype riunione. "
ms.openlocfilehash: 264edbeeaaca9eb2b057760ec6432deedb4b78e4
ms.sourcegitcommit: 08c6fe9955ea61dd9cded2210ae0153e06bdd8a6
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/28/2018
ms.locfileid: "23252527"
---
# <a name="set-up-skype-for-business-online"></a>Configurare Skype for Business online

È necessario disporre delle autorizzazioni di amministratore globale di Office 365 impostare Skype per le aziende. Se si dispone di un firewall o il server proxy che limita l'accesso a Web part del sito web, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per impostare Skype per le aziende automaticamente.

## <a name="setting-up-skype"></a>Impostazione di Skype

Probabilmente hai bisogno di informazioni impostazione Skype la sottoscrizione a Office 365. È possibile seguire i passaggi descritti in questo articolo per ottenere il programma di installazione completata.

## <a name="1-plan-for-skype-for-business"></a>1. pianificare Skype per le aziende

Se si dispone di **[Office 365 Business Premium](https://products.office.com/en-us/business/office-365-business-premium)** o **Business Essentials**, è possibile utilizzare Skype per le aziende a effettuare chiamate online ad altre persone nell'azienda che utilizza la sottoscrizione. Ad esempio, se l'azienda dispone di 10 utenti, sarà possibile iniziare a [utilizzare Skype per le aziende di messaggistica Istantanea e riunioni online](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) e [riunioni con Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) mediante Skype per le aziende dopo aver eseguito i passaggi da 2 a 6 riportata di seguito. E consente di [impostare un Skype per le riunioni aziendali in Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) per riunioni online, troppo!

Se si desidera utilizzare Skype for Business per effettuare e ricevere **chiamate** da utenti *esterni* all'azienda:

- **Opzione 1: puoi usare l'[app Skype](https://www.skype.com/)** gratuita. Se si dispone di un'azienda di dimensioni molto piccola (ad esempio, 1-2 persone), utilizzando l'app Skype è il modo migliore per accedere. È l'opzione più conveniente per effettuare le chiamate nazionali e internazionali. È comunque tenere conferenze telefoniche, effettuare videochiamate e condividere il desktop per le presentazioni. [Estrarre le tariffe e le opzioni di pagamento](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).

- Opzione **2. Aggiornare il piano di acquistare un piano di chiamata e il sistema telefonico per Office 365**. Il modo più semplice per scoprire quanto questo costi e quindi passare, è a [contattare il supporto per i prodotti di business - della Guida di amministrazione](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) e chiedere di effettuare tutte le automaticamente.

Per ulteriori informazioni, vedere [pianificare l'installazione di Office 365 per aziende](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).

## <a name="2-sign-in-to-office-365"></a>2. accedere a Office 365
<a name="bkmk_signin"> </a>

Skype per Business Online fa parte della famiglia di prodotti Office 365 dei servizi. Per configurare Skype Business online, è necessario accedere a Office 365. Ecco come eseguire che:

1. Individuare l'ID utente di Office 365 (ad esempio *rob@fourthcoffee.com* ). È stato ricevuto un messaggio di posta elettronica dal Microsoft Online Services Team che contiene l'ID utente di Office 365 creato quando è stato acquistato Skype Business online. La posta sarà simile al seguente:

    ![Un esempio di messaggio di posta elettronica iniziale è stato ricevuto dopo che è iscritti a Skype Business online. Contiene l'id utente di Office 365.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. Accedere all'interfaccia di amministrazione di Office 365 e immettere la password e l'ID utente di Office 365. Dopo aver effettuato l'accesso, verrà visualizzata l'interfaccia di amministrazione di Office 365:

    ![Un esempio di quali l'interfaccia di amministrazione di Office 365 è simile a quando si dispone di un Skype per pianificare in linea aziendale.](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)

## <a name="3-set-up-your-domain-and-users"></a>3. configurare il dominio e gli utenti
<a name="bkmk_users"> </a>

Ora che è effettuato l'accesso a Office 365, è possibile impostare il dominio e utenti di all'interno dell'organizzazione da utilizzare Skype per Business Online.

1. [Aggiungi un dominio e agli utenti di Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): utilizzare l'installazione guidata di Office 365 per impostare il dominio personalizzato (ad esempio *fourthcoffee.com*) con Office 365. **Per impostazione predefinita, l'installazione guidata di Office 365 include impostazione Skype Business online e la creazione del Skype per gli ID utente aziendali.** Se la procedura guidata già utilizzato per impostare il dominio per Office 365, è stato completato questo passaggio.

2. [Il dominio e le connessioni DNS](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): utilizzare questo strumento - la risoluzione dei problemi domini - per verificare che il dominio e le impostazioni DNS siano corrette. In questo modo ora verrà inoltrate molto come scoprire eventuali problemi di installazione in seguito poiché sarà in grado di eliminare le impostazioni DNS come origine dei problemi futuri.

3. [Office 365 URL e intervalli di indirizzi IP](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): la maggior parte delle piccole imprese non è necessario eseguire questo passaggio. **Ma se si dispone di un server firewall o proxy che limita l'accesso alle Web part del sito web**, è necessario creare le regole per consentire l'accesso per il Skype per gli endpoint Business Online. Questo è un passaggio avanzato eseguito in modo ottimale da un utente si è verificato a configurare Firewall e server proxy. Se non è in precedenza, potrebbe essere necessario rivolgersi un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per impostare Skype per le aziende automaticamente.

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. configurare messaggistica Istantanea e presenza all'interno dell'organizzazione
<a name="bkmk_IM"> </a>

Messaggistica immediata e la presenza ([controllo dell'accesso alle informazioni sulla presenza in Skype per le aziende](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) sono base sulle funzionalità incluse in Skype per le aziende. Per impostazione predefinita, le persone in un'azienda possano Skype e messaggistica immediata tra loro.

1. **Scegliere gli altri utenti che può comunicare il Skype per gli utenti aziendali:**

  - [Consenti agli utenti di contatti esterni Skype per gli utenti aziendali](allow-users-to-contact-external-skype-for-business-users.md) Entrambe si *e* altre attività è necessario configurare i sistemi.

    **Importante**: se si dispone di due domini nell'azienda, ad esempio rob@contosowest.com e ina@contosoeast.com, è necessario eseguire questo passaggio, in modo che tutti gli utenti possono comunicare tra loro.

  - [Consentire Skype per gli utenti aziendali di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md) all'esterno dell'azienda

2. **Scegli utenti che possono se colleghi sono in linea:** La funzionalità di presenza viene illustrato che è in linea e come la loro disponibilità viene, ad esempio disponibile, occupato, non al computer o presentazione.

    ![Un esempio di stato in linea di una persona con un messaggio personale.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    È possibile scegliere le impostazioni predefinite per tutti gli utenti nell'organizzazione:

  - Visualizzare automaticamente la presenza in linea di una persona per tutti gli utenti nell'organizzazione

  - Visualizzare la presenza in linea di una persona solo per i contatti

Per ulteriori informazioni, vedere [Configure la presenza in Skype Business online](configure-presence-in-skype-for-business-online.md).

## <a name="5-download-and-install-skype-for-business"></a>5. scaricare e installare Skype per le aziende
<a name="bkmk_download"> </a>

Per utilizzare Skype per le aziende su PC, Mac o dispositivo mobile, si e altre persone nell'azienda è necessario installare innanzitutto Skype per il download del Business nei dispositivi.

- [Installare Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): istruzioni su come scaricare l'app dal portale di Office 365 e installarlo nel PC o Mac.

- [Deploy Skype per client di Business in Office 365](deploy-the-skype-for-business-client-in-office-365.md): istruzioni per la distribuzione dell'app in un'azienda di grandi dimensioni.

- [Installare Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): scaricare, installare e accedere a Skype for Business nei dispositivi Android, dispositivi iOS e Windows Phone.

- [Attivare o disattivare le notifiche di cellulare](turn-on-or-off-mobile-phone-notifications.md): quando si dispone di Skype per le aziende installata su un dispositivo mobile, è e altre persone nell'azienda può ricevere avvisi relativi a messaggi immediati in arrivo e senza risposta.

## <a name="6-test-to-make-sure-everything-is-working"></a>6. eseguire il test per verificare che tutto funzioni
<a name="bkmk_test"> </a>

Per prima cosa, verificare se altri utenti nell'azienda possono [Video: effettuare l'accesso e la disconnessione da Skype per le aziende](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451). Verificare la possibilità di messaggistica immediata ogni altro, vedere la presenza reciproca e provare a una riunione veloce.

Problemi? Eseguire le operazioni seguenti:

- [Bisogno di assistenza per l'accesso a Skype per le aziende?](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05) dei problemi comuni di accesso.

- [Contattare il supporto per i prodotti di business - della Guida di amministrazione](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Siamo a tua disposizione per!

## <a name="do-you-want-to-set-up-other-available-features"></a>Si desidera impostare le altre caratteristiche disponibili?
<a name="bkmk_more"> </a>

Prima di impostare le altre funzionalità, verificare che siano disponibili licenze per tali. [Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md)

### <a name="set-up-audio-conferencing"></a>Configurare l'audioconferenza

Talvolta le persone all'interno dell'organizzazione dovranno usare un telefono per accedere a una riunione. Skype per le aziende include la funzionalità di audioconferenza per solo questa situazione! Le persone possono accedere alle riunioni di Skype for Business usando un telefono, al posto di usare la app di Skype for Business su un dispositivo mobile o PC.

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Configurazione di sistema telefonico e i piani di chiamata in Office 365

La caratteristica di sistema telefonico in Office 365 offre un sistema telefonico per la propria azienda. Le chiamate per gli altri Skype per gli utenti aziendali all'interno dell'organizzazione sono gratuite e i dipendenti possono ricevere messaggi vocali tra loro e i chiamanti esterni. Ecco cosa viene visualizzato con sistema telefonico.

Quando si aggiunge il servizio prevede la chiamata, i dipendenti ottengono un numero di telefono principale in Skype per le aziende. È possibile effettuare e ricevere chiamate telefoniche di fuori dell'azienda. Si possono effettuare chiamate vocali in telefoni VoIP, PC e dispositivi mobili. E, in caso di emergenza, è possibile chiamare 911 per la Guida.

Per le istruzioni dettagliate, vedere Set up prevede la chiamata.

### <a name="set-up-skype-meeting-broadcast"></a>Configurazione di trasmissione riunione Skype

Skype riunione trasmissione è una funzionalità che consente di generare, host e trasmissione riunioni con partecipanti fino a 10.000. **Per ulteriori informazioni su come utilizzarlo, vedere [che cos'è una riunione Skype trasmissione?](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**

Di seguito viene fornita una panoramica dei passaggi per configurare trasmissione riunione Skype:

1. [Assegnare o rimuovere licenze per Office 365 per aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): assegnare licenze **Skype Business online** o si **Prevede di organizzazione** a tutti gli utenti verranno per **ospitare** una riunione di trasmissione.

2. [Abilitare trasmissione riunione Skype](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): per impostazione predefinita, questa funzionalità non è attivata. Una volta abilitata, gli utenti saranno in grado di ospitare le riunioni trasmissione con altre persone nell'organizzazione.

3. [Configurazione di rete per la trasmissione riunione Skype](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): se si desidera webinar host e altre trasmissioni con partecipanti esterni all'organizzazione, è necessario configurare la rete.

4. [Pianifica riunione trasmissione Skype](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) e dispongono di un [Join la trasmissione di una riunione Skype](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): effettuare riunioni verificare trasmissione utilizzare pianificando una trasmissione riunione Skype al *https://portal.broadcast.skype.com* e fare in modo che un utente tenta di partecipare alla riunione.

## <a name="learn-about-network-connectivity-requirements"></a>Informazioni sui requisiti di connettività di rete
<a name="bkmk_more"> </a>

La qualità dell'audio, video e Skype per le aziende di condivisione applicazioni è notevolmente interessata dalla qualità della connettività di rete end-to-end. Per un'esperienza ottimale, è importante assicurarsi che vi sia una connessione di alta qualità tra la rete aziendale e Skype Business online. Per la rete e ottimizzazione delle informazioni, vedere [Ottimizzare Skype per ottenere prestazioni aziendali in linea](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>Operazioni completate configurazione? Guida introduttiva all'utilizzo Skype per le aziende
<a name="bkmk_more"> </a>

[Skype per la formazione per soluzioni aziendali](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): estrarre questo elenco di argomenti di formazione per iniziare rapidamente!

[Avviare un Skype Business conferenza telefonica](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[Impostare le opzioni del dispositivo Video in Skype per le aziende](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[Effettuare e ricevere una videochiamata tramite Skype per le aziende](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Argomenti correlati
<a name="bkmk_more"> </a>

[Pianificare la connettività ibrida tra Skype per Business Server e Skype Business online](https://go.microsoft.com/fwlink/p/?linkid=400791)



