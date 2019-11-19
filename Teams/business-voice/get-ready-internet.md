---
title: Controllare la connessione Internet
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 19f26c0bd7ab4fe89770909d81d60abc97aaa8b0
ms.sourcegitcommit: 4a4ed872eff22663720296ae29c0e644286857f2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/15/2019
ms.locfileid: "38653552"
---
# <a name="check-your-internet-connection"></a>Controllare la connessione Internet

VoIP aziendale si trova nel cloud con Microsoft 365. Ogni computer e dispositivo che usa Microsoft Teams e VoIP aziendale richiede una connessione a Internet. Per ottenere risultati ottimali con VoIP aziendale, è necessaria una connessione Internet a banda larga in grado di supportare il numero previsto di chiamate telefoniche che verranno eseguite in qualsiasi momento. È anche necessario assicurarsi che i computer della rete possano accedere ai server Microsoft 365.

Per eseguire questa procedura, è necessario avere un tenant con uno degli abbonamenti seguenti:

* Office 365 Business Essentials
* Office 365 Business Premium
* Office 365 E1
* Office 365 E3
* Office 365 F1
* Microsoft 365 A1
* Microsoft 365 A3
* Microsoft 365 E3
* Microsoft 365 Business

Non è necessaria una licenza VoIP aziendale per eseguire questa procedura.

## <a name="check-your-internet-connection-speed"></a>Controllare la velocità della connessione Internet

Questo articolo illustra come determinare se la connessione Internet è abbastanza veloce per il numero di persone che devono effettuare chiamate telefoniche, organizzare videoconferenze e così via. Immettendo alcune informazioni sull'organizzazione è possibile ottenere un report con la quantità di connessione Internet che verrà usata da Teams e da VoIP aziendale.

### <a name="get-information-about-your-internet-connection-and-users"></a>Ottenere informazioni sulla connessione Internet e sugli utenti

Prima di iniziare, è necessario disporre delle informazioni seguenti:

* La velocità della connessione Internet.
* Quante persone useranno VoIP aziendale principalmente dall'ufficio.
* Quante persone useranno VoIP aziendale principalmente da una posizione remota, come un ufficio a casa.

### <a name="enter-your-information-into-the-network-planner"></a>Immettere le informazioni nel Network Planner

Ecco cosa fare:

1. Aprire il browser e passare a https://admin.teams.microsoft.com, quindi accedere con un account dotato di autorizzazioni di amministratore globale. L'account usato per iscriversi a Office 365 dispone di queste autorizzazioni.
1. Aprire **Pianificazione** e poi selezionare **Network planner**.
1. In **Piani di rete** selezionare **Aggiungi**. Assegnare un nome al piano e quindi selezionare **Applica**. Il piano di rete dovrebbe essere simile a questo:

    ![Schermata principale di Network Planner](../media/network-planner-main.png)
1. Fare clic sul nome del piano di rete, **Ufficio principale** nell'immagine sopra.
1. Nella pagina successiva selezionare **Aggiungi un sito di rete** nella scheda **Siti di rete**.
1. Compilare solo i campi indicati nella schermata seguente e poi selezionare **Salva**. Lasciare vuoti gli altri campi della schermata e non selezionare le opzioni **ExpressRoute** o **Connesso a WAN**.

    ![Informazioni sul sito di Network Planner](../media/network-planner-site-info.png)
1. Nella scheda **Report** selezionare **Avviare un report**.
1. Compilare le informazioni seguenti e poi selezionare **Genera rapporto** per creare un report con i requisiti di larghezza di banda per Teams. Mostreremo come leggere il report nella sezione successiva.

    ![Informazioni sul report di Network Planner](../media/network-planner-report-info.png)

### <a name="find-your-minimum-internet-connection-speed"></a>Trovare la velocità minima della connessione Internet

Dopo aver selezionato **Genera report**, Office 365 crea un report simile al seguente:

![Dettagli sul report di Network Planner](../media/network-planner-report.png)

Il numero evidenziato indica la quantità di connessione Internet che Teams e VoIP aziendale useranno. Si consiglia di non superare il 30% della velocità totale della connessione Internet. Ad esempio, se la connessione Internet è di 60 Mbps, Teams e VoIP aziendale non devono usare più di 18 Mbps.

Per determinare la velocità minima della connessione Internet, eseguire questo calcolo: `<highlighted number> / .3`. Usando il numero evidenziato nell'immagine sopra, il calcolo sarebbe `4.6875 / .3 = 15.6`. Ciò significa che la velocità minima della connessione Internet deve essere di 15,6 Mbps.

Se Teams e VoIP aziendale usano più del 30% della velocità totale della connessione Internet, il numero evidenziato verrà visualizzato in rosso. In questo caso, potrebbe essere necessario eseguire l'aggiornamento della connessione Internet.

![Avviso velocità della connessione](../media/network-planner-report-speed-warning.png)

## <a name="make-sure-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Assicurarsi che i computer e i dispositivi della rete possano raggiungere Microsoft 365

Per funzionare correttamente, i computer e i dispositivi che si vogliono usare con VoIP aziendale devono comunicare con i server di Microsoft 365 usando specifiche porte di rete. Le porte di rete sono, in poche parole, porte che consentono a computer e dispositivi di comunicare tra di loro tramite una rete o Internet. Il firewall deve consentire ai computer e ai dispositivi della rete di raggiungere Microsoft 365 usando le porte di rete in uscita seguenti:

* **porte TCP** 80 e 443
* **Porte UDP** 3478, 3479, 3480 e 3481

Il modo più semplice per verificare se il firewall consente la comunicazione tra queste porte di rete è quello di effettuare una chiamata di prova con Teams. Per effettuare una chiamata di prova, eseguire le operazioni seguenti:

1. Passare a https://aka.ms/getteams in un computer della rete per installare Teams. Assicurarsi che gli altoparlanti e il microfono siano connessi al computer.
2. Aprire Teams ed eseguire l'accesso con un account Microsoft 365
3. In Teams selezionare l'immagine del profilo, quindi **Impostazioni** > **Dispositivi**
4. Scegliere **Effettua una chiamata di prova** in **Dispositivi audio**
5. Seguire le istruzioni visualizzate per inviare un messaggio e riascoltarlo

* Se la chiama si connette ed si sente il messaggio riprodotto, il firewall è configurato correttamente.
* Se la chiamata si connette, ma non si sentono le istruzioni o il messaggio riprodotto, verificare che gli altoparlanti e il microfono siano configurati correttamente e che vengano rilevati dal computer. Riprovare.
* Se la chiamata non si connette o se si connette ma non si sente il messaggio riprodotto, potrebbe essere necessario aggiornare il firewall per autorizzare le porte di rete elencate in precedenza. Consultare la documentazione del firewall su come consentire alle porte di rete di raggiungere Internet o rivolgersi a un tecnico informatico per assistenza.

Se si è un professionista informatico e si vogliono ottenere altre informazioni su come preparare reti più grandi o complesse per supportare VoIP aziendale, vedere [Valutare l'ambiente](../3-envision-evaluate-my-environment.md). L’articolo [Valutare l'ambiente](../3-envision-evaluate-my-environment.md) fornisce informazioni aggiuntive sui requisiti di larghezza di banda, proxy e firewall e anche su come testare la rete con lo [Strumento di valutazione della rete](../3-envision-evaluate-my-environment.md#test-the-network).
