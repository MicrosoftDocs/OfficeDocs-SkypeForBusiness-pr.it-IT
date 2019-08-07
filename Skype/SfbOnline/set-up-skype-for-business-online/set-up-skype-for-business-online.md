---
title: Configurare Skype for Business online
ms.reviewer: ''
ms.author: tonysmit
author: tonysmit
manager: serdars
ms.topic: article
ms.assetid: 40296968-e779-4259-980b-c2de1c044c6e
ms.tgt.pltfrm: cloud
ms.service: skype-for-business-online
search.appverid: MET150
ms.collection: Adm_Skype4B_Online
audience: Admin
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
description: "Informazioni su come configurare il dominio, gli utenti, la messaggistica Istantanea e la presenza dell'organizzazione per l'installazione di Skype for Business.  Vedere anche Informazioni su come Configurazione di conferenze Audio, Sistema telefonico e Piani di chiamata e Skype Meeting broadcast. "
ms.openlocfilehash: 239e1c39563594ffe1ff106284bbbf912367fb88
ms.sourcegitcommit: ca1ac291ab6394f050b9b517d9f3906f3a970b04
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/06/2019
ms.locfileid: "35792621"
---
# <a name="set-up-skype-for-business-online"></a>Configurare Skype for Business online

Per eseguire questa procedura, è necessario avere le autorizzazioni di amministratore globale di Office 365 per Skype for Business. Se si dispone di un server proxy o firewall che limita l'accesso a parti del sito web, è consigliabile affidarsi a un [partner Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) configurare Skype for Business automaticamente.

## <a name="setting-up-skype"></a>Impostare Skype

Serve aiuto per configurare Skype con l'abbonamento a Office 365? È possibile seguire la procedura descritta in questo articolo per completare la configurazione.

## <a name="1-plan-for-skype-for-business"></a>1. Pianificare Skype for Business 

Con **[Office 365 Business Premium](https://products.office.com/it-IT/business/office-365-business-premium)** o ** Business Essentials**, è possibile usare Skype for Business per effettuare chiamate ad altre persone dell'azienda incluse nell'abbonamento. Ad esempio, se l'azienda ha 10 dipendenti, sarà possibile [Iniziare a usare Skype for Business per la messaggistica Istantanea e riunioni online](https://support.office.com/article/cc05afa6-1894-4a82-9dd9-6222061f50fd) tra loro, e [Riunioni con Skype for Business](https://support.office.com/article/2eed8424-581a-4497-b505-c08c152e5851) usando Skype for Business dopo ave eseguito i passaggi da 2 a 6, descritti qui sotto. È possibile [Impostare una Riunione in Skype for Business su Outlook](https://support.office.com/article/b8305620-d16e-4667-989d-4a977aad6556#bkmk_OWA) oltre alle riunioni online!

Se si desidera usare Skype for Business per effettuare e ricevere **chiamate** da persone*esterne* all'azienda:

- **Opzione 1. Usare il software gratuito [app Skype](https://www.skype.com/)**. Se hai un'azienda molto piccola (composta, ad esempio, da 1 o 2 persone), l'utilizzo dell'app Skype è la soluzione migliore. L'app è infatti meno costosa da usare per le chiamate nazionali e internazionali. È comunque possibile tenere conferenze telefoniche, effettuare videochiamate e condividere il desktop per le presentazioni. [Scopri le tariffe e le opzioni di pagamento](https://secure.skype.com/en/calling-rates?wt.mc_id=legacy&amp;expo365=bundled).

- **Opzione 2. Aggiornare il piano e acquistare Sistema telefonico e Piano di chiamata per Office 365**. Il modo migliore per conoscerne il costo effettivo ed effettuare il cambio è di [Contattare il supporto per i prodotti per le aziende - Guida per gli amministratori](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b) che esegua queste operazioni per l’utente.

Per ulteriori informazioni, vedere [Pianificare la configurazione di Office 365 per le aziende](https://support.office.com/article/eb926624-018b-4486-bf11-5fba6ee4d645#bkmk_skype).

## <a name="2-sign-in-to-office-365"></a>2. Accedere a Office 365
<a name="bkmk_signin"> </a>

Skype for Business online fa parte della famiglia di servizi di Office 365. Per configurare Skype for Business online, è necessario effettuare l'accesso a Office 365. Ecco come si esegue questa operazione:

1. Trovare l'ID utente di Office 365 (ad esempio, <em>rob@fourthcoffee.com</em> ). Si riceve un messaggio di posta elettronica dal Team di Microsoft Online Services che contiene l'ID utente di Office 365 creato al momento dell'acquisto Skype for Business online. L'aspetto della email dovrebbe essere simile a questo:

    ![Esempio del messaggio di posta elettronica di benvenuto che si riceve dopo essersi iscritti a Skype for Business online. Contiene l'ID utente di Office 365.](../images/977c5c96-29c5-40c0-a4c4-1ba66ba3a1fb.png)

2. Accedere all'interfaccia di amministrazione e immettere l'ID utente di Office 365 e la password. Dopo l'accesso, verrà visualizzata l'interfaccia di amministrazione di Microsoft 365:

    ![Esempio dell'aspetto dell'interfaccia di amministrazione di quando si ha un piano di Skype for Business online.](../images/ed1d9906-e717-450b-81a3-ce6679bd1be1.png)

## <a name="3-set-up-your-domain-and-users"></a>3. Configurare il dominio e gli utenti
<a name="bkmk_users"> </a>

Ora che è connessi a Office 365, è possibile impostare il dominio e gli utenti dell'organizzazione con Skype for Business online.

1. [Aggiungere dominio e utenti a Office 365](https://support.office.com/article/6383f56d-3d09-4dcb-9b41-b5f5a5efd611): usare la configurazione guidata di Office 365 per configurare il dominio personalizzato (ad esempio *fourthcoffee.com*) con Office 365. **Per impostazione predefinita, la configurazione guidata di Office 365 include la configurazione di Skype for Business online e la creazione dell’ID utente di Skype for BusinessS** Se la procedura guidata è stata già usata per configurare il dominio per Office 365, questo passaggio è da considerarsi completato.

2. [Verificare le connessioni DNS e il dominio](https://support.office.com/article/2b54e1b0-47a7-4018-a1e4-c2b924e7c5a0): usare lo strumento, la risoluzione dei problemi dei domini, per verificare che il dominio e le impostazioni DNS siano corrette. Questa operazione effettuata ora contribuirà ad individuare eventuali problemi di installazione che potrebbero presentarsi in un secondo momento, poiché è possibile eliminare le impostazioni DNS come origine di futuri problemi.

3. [URL e intervalli di indirizzi IP di Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2#BKMK_LYO): per la maggior parte delle aziende non è necessario eseguire questo passaggio. **Se invece si ha un server proxy o firewall che limita l'accesso a parti del sito web**, è necessario creare regole per consentire l'accesso agli endpoint di Skype for Business online. Si tratta di un passaggio di livello avanzato meglio eseguito da utenti esperti di configurazione di firewall e server proxy. Se non è stato ancora eseguito, è consigliabile affidarsi a un [partner di Microsoft](https://go.microsoft.com/fwlink/?linkid=391089) per configurare Skype for Business automaticamente.

## <a name="4-set-up-im-and-presence-in-your-organization"></a>4. Configurazione della messaggistica istantanea e la presenza della propria organizzazione
<a name="bkmk_IM"> </a>

La messaggistica istantanea e la presenza ([Controllare l'accesso alle informazioni sulla presenza in Skype for Business](https://support.office.com/article/fea86e34-60cf-4dd0-bfb2-169a42afd92c)) sono le caratteristiche di base incluse in Skype for Business. Per impostazione predefinita, gli utenti dell'organizzazione possono usare Skype e la messaggistica Istantanea tra loro.

1. **Scegliere con quali altri utenti possono comunicare gli utenti di Skype for Business:**

   - [Consentire agli utenti di contattare utenti Skype for Business esterni](allow-users-to-contact-external-skype-for-business-users.md) Sia l’utente *che* le altre aziende dovranno configurare il sistema.

     **IMPORTANTE**: se sono presenti due domini dell'organizzazione, ad esempio rob@contosowest.com e ina@contosoeast.com, è necessario eseguire questa procedura, affinché tutti gli utenti possano comunicare tra loro.

   - [Consentire agli utenti di Skype for Business di aggiungere contatti Skype](let-skype-for-business-users-add-skype-contacts.md)esterni all’azienda.

2. **Scegliere chi può vedere se i propri colleghi sono in linea:** La funzionalità di presenza mostra gli utenti in linea e la loro disponibilità, ad esempio disponibile, occupato, non al computer o presentazione in corso.

    ![Esempio di un utente in linea con un messaggio personale.](../images/ab6c10b4-6ad5-453c-bf0e-459b977b6e23.png)

    È possibile scegliere le impostazioni predefinite per tutti gli utenti dell'azienda:

   - Visualizzare automaticamente la presenza di una persona in linea per tutti gli utenti dell'organizzazione

   - Visualizzare la presenza online di un utente solo per i suoi contatti

Per istruzioni, vedere [Configurare la presenza in Skype for Business online](configure-presence-in-skype-for-business-online.md).

## <a name="5-download-and-install-skype-for-business"></a>5. Scarica e installa Skype for Business
<a name="bkmk_download"> </a>

Per utilizzare Skype for Business nel PC, Mac o in un dispositivo mobile, è necessario installare nei dispositivi dell’utente e delle altre persone all’interno dell’azienda il file di installazione di Skype for Business.

- [Installare Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): Istruzioni per scaricare l'applicazione dal portale di Office 365 e installarlo nel PC o Mac.

- [Distribuire Skype for Business client di Office 365](deploy-the-skype-for-business-client-in-office-365.md): istruzioni per la distribuzione dell'applicazione in una grande azienda.

- [Installare Skype for Business](https://support.office.com/article/8a0d4da8-9d58-44f9-9759-5c8f340cb3fb): scaricare, installare e accedere a Skype for Business su dispositivi Android, iOS e telefoni Windows.

- [Attivare o disattivare le notifiche per cellulari](turn-on-or-off-mobile-phone-notifications.md): nel caso di Skype for Business installato su un dispositivo mobile, gli utenti possono ricevere notifiche sui messaggi istantanei in arrivo e messaggi persi.

## <a name="6-test-to-make-sure-everything-is-working"></a>6. Verificare che tutto funzioni correttamente
<a name="bkmk_test"> </a>

Prima di tutto, verificare se altri utenti dell'organizzazione possano [Video: accedere a Skype for Business](https://support.office.com/article/8abed4b3-ac48-493e-9d76-0e10140e9451). Verificare che gli utenti possano inviarsi un messaggio istantaneo tra loro, vedere la presenza degli altri e provare a eseguire una rapida riunione.

Problemi? Effettuare le seguenti operazioni:

- [Occorrono indicazioni per l'accesso a Skype for Business](https://support.office.com/article/448b8ea7-5b33-444a-afd4-175fc9930d05)tra i comuni problemi di accesso.

- [Contattare il supporto tecnico per i prodotti per le aziende - Guida dell’amministratore](https://support.office.com/article/32a17ca7-6fa0-4870-8a8d-e25ba4ccfd4b). Opzioni di assistenza

## <a name="do-you-want-to-set-up-other-available-features"></a>Si desidera configurare altre caratteristiche disponibili?
<a name="bkmk_more"> </a>

Prima di configurare altre caratteristiche, assicurarsi di avere le relative licenze. [Licenze per i componenti aggiuntivi Skype for Business e Microsoft Teams](../skype-for-business-and-microsoft-teams-add-on-licensing/skype-for-business-and-microsoft-teams-add-on-licensing.md).

### <a name="set-up-audio-conferencing"></a>Configurare l’audioconferenza

In alcuni casi gli utenti dell'organizzazione dovranno usare il telefono per partecipare a una riunione. Skype for Business e Microsoft Teams offrono la funzione di Audioconferenza proprio per queste evenienze! Le persone possono accedere alle riunioni di Skype for Business usando un telefono, al posto di usare la app di Skype for Business su un dispositivo mobile o PC.

### <a name="set-up-phone-system-and-the-calling-plans-in-office-365"></a>Impostare un sistema telefonico e i Piani di chiamata in Office 365

La funzione di sistema telefonico in Office 365 offre un sistema di telefonia per l'azienda. Le chiamate ad altri utenti Skype for Business nella tua organizzazione sono gratuite e i dipendenti possono ricevere messaggi vocali tra di loro e da utenti provenienti dall’esterno. Vantaggi offerti dal Sistema telefonico.

Quando si aggiunge il piano di chiamata, i dipendenti ottengono un numero di telefono principale su Skype for Business. È possibile effettuare e ricevere chiamate telefoniche all'esterno dell'azienda. Gli utenti possono effettuare chiamate vocali tramite telefoni VoIP, PC e dispositivi mobili. E, in caso di emergenza, possono chiamare il 911 per assistenza.

Per istruzioni dettagliate, vedere Impostare Piani di chiamata.

### <a name="set-up-skype-meeting-broadcast"></a>Configurare Skype Meeting Broadcast

Skype Meeting Broadcast consente di produrre, ospitare e trasmettere riunioni fino a 10.000 partecipanti. **Per ulteriori informazioni su come funziona, vedere [Informazioni su Skype Meeting Broadcast](https://support.office.com/article/c472c76b-21f1-4e4b-ab58-329a6c33757d)**

Ecco una panoramica dei passaggi per configurare Skype Meeting Broadcast:

1. [Assegnare o rimuovere licenze per Office 365 per le aziende](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc): assegnare licenze per**Skype for Business online** o **Enterprise Plan** a tutti gli utenti che **ospiteranno**una riunione Broadcast.

2. [Abilitare Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/enable-skype-meeting-broadcast.md): per impostazione predefinita, questa caratteristica non è abilitata. Una volta attivata, gli utenti potranno organizzare riunioni broadcast con altre persone che fanno parte dell’organizzazione.

3. [Configurare la rete per Skype Meeting Broadcast](../set-up-your-network-for-skype-meeting-broadcast/set-up-your-network-for-skype-meeting-broadcast.md): se si desidera ospitare webinar e altre trasmissioni con partecipanti esterni all’organizzazione, è necessario configurare la rete.

4. [Pianificare una riunione con Skype Meeting Broadcast](https://support.office.com/article/c3995bc9-4d32-4f75-a004-3bc5c477e553) e  [Unirsi a Skype Meeting Broadcast](https://support.office.com/article/14689da0-821d-48d4-9035-ea762de80ebe): assicurarsi che le riunioni broadcast funzionino pianificando una riunione su Skype Meeting Broadcast con * https://portal.broadcast.skype.com * e chiedendo a qualcuno di provare a partecipare alla riunione.

## <a name="learn-about-network-connectivity-requirements"></a>Informazioni sui requisiti di connettività di rete
<a name="bkmk_more"> </a>

La qualità di audio, video e condivisione delle applicazioni non è soddisfacente? Le prestazioni di Skype for Business sono notevolmente influenzate dalla qualità della connettività di rete end-to-end. Per un'esperienza ottimale, è importante verificare che la connessione tra la propria azienda e Skype for Business online sia di alta qualità. Per informazioni sulla connessione e la regolazione, vedere [Ottimizzare le prestazioni di Skype for Business online](https://support.office.com/article/beec23c2-c5d6-4e84-a8af-e82aefca7802).

## <a name="all-done-setting-up-getting-started-using-skype-for-business"></a>Configurazione completata? Iniziare ad usare Skype for Business
<a name="bkmk_more"> </a>

[Formazione su Skype for Business](https://support.office.com/article/8a3491a3-c095-4718-80cf-cbbe4afe4eba): controllare questo elenco di argomenti di formazione per iniziare rapidamente l’utilizzo.

[Avviare una conferenza telefonica Skype for Business](https://support.office.com/article/8dc8ac52-91ac-4db9-8672-11551fdaf997)

[Video: Impostare le opzioni di presenza in Skype for Business](https://support.office.com/article/d09017c0-deba-4f6c-a122-9eca6604f50c)

[Effettuare e ricevere videochiamate con Skype for Business](https://support.office.com/article/abf62493-670f-4b0d-b2cf-fe03b49caf42)

[!INCLUDE [LinkedIn Learning Info](../../common/office/linkedin-learning-info.md)]

## <a name="related-topics"></a>Argomenti correlati
<a name="bkmk_more"> </a>

[Pianificare la connettività ibrida tra Skype for Business Server e Skype for Business online](https://go.microsoft.com/fwlink/p/?linkid=400791)



