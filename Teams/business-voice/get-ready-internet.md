---
title: Controllare la connessione Internet per Sistema telefonico teams
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
search.appverid: MET150
description: Verificare che internet sia pronto per il sistema telefonico di Teams
appliesto:
- Microsoft Teams
ms.collection:
- M365-voice
ms.openlocfilehash: 5cbc8613a91e2b776faff922fb9a3a98b3dd545e
ms.sourcegitcommit: 173bdbaea41893d39a951d79d050526b897044d5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/07/2022
ms.locfileid: "67271051"
---
# <a name="check-your-internet-connection-for-teams-phone-system"></a>Controllare la connessione Internet per Sistema telefonico teams

Teams Phone System è la tecnologia di Microsoft per abilitare le funzionalità del telefono all'interno di Microsoft Teams usando il cloud Microsoft 365. Ogni dispositivo che usa Microsoft Teams e Sistema telefonico richiede una connessione a Internet.

Per ottenere la migliore esperienza di Sistema telefonico, è necessaria una connessione Internet a banda larga in grado di supportare il numero massimo di telefonate che l'organizzazione potrebbe effettuare in qualsiasi momento. È anche necessario assicurarsi che i computer della rete possano raggiungere i servizi di Microsoft 365.

## <a name="check-your-internet-connection-speed"></a>Controllare la velocità della connessione Internet

Questo articolo consente di determinare se la connessione Internet è sufficientemente veloce per il numero di persone che devono effettuare telefonate. Fornirai informazioni sulla tua organizzazione e riceverai un report che mostra la quantità di connessione Internet che verrà utilizzata da Teams e sistema telefonico.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Raccogliere informazioni sulla connessione Internet e sugli utenti

Prima di iniziare, è necessario disporre delle informazioni seguenti:

* La velocità della connessione Internet
* Quante persone utilizzeranno sistema telefonico principalmente dal tuo ufficio
* Quante persone utilizzeranno sistema telefonico principalmente da una posizione remota, ad esempio un ufficio di casa

### <a name="enter-your-information-into-the-network-planner"></a>Immettere le informazioni in Network Planner

Eseguire la procedura seguente:

1. In un browser, accedere a [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). Accedere con un account dotato di autorizzazioni di amministratore globale. L'account usato per iscriversi a Microsoft 365 dispone di queste autorizzazioni.
2. Aprire **Pianificazione** e selezionare **Network Planner**.
3. In **Piani di rete** selezionare **Aggiungi**. Immettere un nome per il piano e quindi selezionare **Applica**.
4. Selezionare il nome del piano di rete.
5. Nella pagina successiva selezionare **Aggiungi un sito di rete** nella scheda **Siti di rete**.
6. Compilare i campi **Nome sito di rete**, **Utenti di rete** e **Capacità collegamento Internet** e quindi selezionare **Salva**. Lasciare vuoti gli altri campi della schermata e non selezionare le opzioni **ExpressRoute** o **Connesso a WAN**.
7. Nella scheda **Report** selezionare **Avviare un report**.
8. Immettere il **nome** di un report e il numero di **utenti di rete** (**Office** e **Remote**), quindi selezionare **Genera report** per creare un report che mostri i requisiti di larghezza di banda per Teams. Ti spiegheremo come leggere il report nella prossima sezione.

### <a name="find-your-minimum-internet-connection-speed"></a>Individuare la velocità minima di connessione Internet

Quando si seleziona **Genera report**, Microsoft 365 crea un report.

Sotto la colonna **Impatto** e nella riga **Office 365**, questo numero mostra la quantità di connessione Internet che Useranno Teams e Sistema telefonico. È consigliabile che questo numero non sia superiore al 30% della velocità totale della connessione Internet. Ad esempio, se la connessione Internet è *di 60 Mbps*, Teams e Sistema telefonico non devono utilizzare più di *18 Mbps*.

Usare questa equazione per determinare la velocità minima di connessione Internet: <*Numero di impatto>/0,3*.  

Si supponga che il numero di impatto sia *4,6875 Mbps*. Il calcolo per trovare la velocità minima di connessione Internet è *4,6875 /0,3 = 15,6*. In questo caso, la velocità della connessione Internet deve essere di almeno *15,6 Mbps*.

Se Teams e Sistema telefonico utilizzeranno più del 30% della velocità totale della connessione Internet, il numero **di impatto** apparirà rosso. In questo caso, potrebbe essere necessario aggiornare la connessione Internet.

![Avviso velocità della connessione.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> L'impatto sulla larghezza di banda fornito da Network Planner è solo una stima. Si consiglia di usare [Call Quality Dashboard](../cqd-what-is-call-quality-dashboard.md) per monitorare attivamente l'esperienza utente per le chiamate audio e video con Microsoft Teams all'interno dell'organizzazione.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Assicurarsi che i computer e i dispositivi della rete possano raggiungere Microsoft 365

I computer e i dispositivi che utilizzano Sistema telefonico devono utilizzare porte di rete specifiche per comunicare con i servizi di Microsoft 365. Queste porte sono essenzialmente porte attraverso le quali i dispositivi si parlano tramite una rete o Internet. Il firewall deve consentire ai dispositivi della rete di raggiungere Microsoft 365 usando le porte di rete *in uscita* seguenti:

* **porte TCP** 80 e 443
* **Porte UDP** 3478, 3479, 3480 e 3481

Il modo più semplice per verificare se il firewall consente la comunicazione su queste porte di rete consiste nell'eseguire un test di connettività usando [lo strumento di connettività di rete microsoft 365](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) dalla posizione dell'ufficio da testare. Dopo aver completato il test, verifica i risultati e i suggerimenti.
