---
title: Controlla la tua connessione Internet per Teams Telefono piano chiamate
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
ms.localizationpriority: medium
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: 5f28350c2ae0487ed62d55bbd99d6a731a7bfac0
ms.sourcegitcommit: a969502c0a5237caf041d7726f4f1edefdd75b44
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2022
ms.locfileid: "61766919"
---
# <a name="check-your-internet-connection-for-teams-phone"></a>Controllare la connessione Internet per Teams Telefono

Teams Telefono è la tecnologia Microsoft per l'abilitazione delle funzionalità telefoniche all'interno Microsoft Teams tramite Microsoft 365 cloud. Ogni dispositivo che usa Microsoft Teams e Teams Telefono richiede una connessione a Internet.

Per ottenere la migliore esperienza Teams Telefono, è necessaria una connessione Internet a banda larga in grado di supportare il numero massimo di chiamate telefoniche che l'organizzazione potrebbe effettuare in qualsiasi momento. È anche necessario assicurarsi che i computer della rete possano raggiungere Microsoft 365 servizi.

Non è necessaria una licenza Teams Telefono per eseguire questa procedura.

## <a name="check-your-internet-connection-speed"></a>Controllare la velocità della connessione Internet

Questo articolo consente di determinare se la connessione Internet è abbastanza veloce per il numero di persone che devono effettuare chiamate telefoniche. Si forniranno informazioni sull'organizzazione e si riceverà un report che mostra la quantità di connessione Internet che verrà usata da Teams e Teams Telefono.

### <a name="gather-information-about-your-internet-connection-and-users"></a>Raccogliere informazioni sulla connessione Internet e sugli utenti

Prima di iniziare, è necessario disporre delle informazioni seguenti:

* La velocità della connessione Internet
* Quante persone useranno Teams Telefono principalmente dall'ufficio
* Quante persone useranno Teams Telefono principalmente da una posizione remota, ad esempio un ufficio di casa

### <a name="enter-your-information-into-the-network-planner"></a>Immettere le informazioni in Network Planner

Eseguire la procedura seguente:

1. In un browser, accedere a [https://admin.teams.microsoft.com](https://admin.teams.microsoft.com). Accedere con un account dotato di autorizzazioni di amministratore globale. L'account usato per iscriversi a Microsoft 365 o Office 365 dispone di queste autorizzazioni.
2. Aprire **Pianificazione** e selezionare **Network Planner**.
3. In **Piani di rete** selezionare **Aggiungi**. Immettere un nome per il piano e quindi selezionare **Applica**.
4. Selezionare il nome del piano di rete.
5. Nella pagina successiva selezionare **Aggiungi un sito di rete** nella scheda **Siti di rete**.
6. Compilare i **campi Nome sito di rete**, Utenti **di** rete e **Capacità collegamento Internet** e quindi selezionare **Salva**. Lasciare vuoti gli altri campi della schermata e non selezionare le opzioni **ExpressRoute** o **Connesso a WAN**.
7. Nella scheda **Report** selezionare **Avviare un report**.
8. Immettere un **nome di report** e il numero di utenti di rete (**Office** **e** remoto ), quindi selezionare Genera **report** per creare un report che mostra i requisiti di larghezza di banda per Teams.  Nella sezione successiva verrà spiegato come leggere il report.

### <a name="find-your-minimum-internet-connection-speed"></a>Trovare la velocità minima di connessione Internet

Quando si seleziona **Genera report,** Microsoft 365 o Office 365 crea un report.

Nella colonna **Impatto** e nella riga **Office 365,** questo numero mostra la quantità di connessioni Internet Teams e Teams Telefono utilizzeranno. È consigliabile che questo numero non sia superiore al 30% della velocità totale della connessione Internet. Ad esempio, se la connessione Internet è *a 60 Mbps,* Teams e Teams Telefono non devono usare più di *18 Mbps.*

Usare questa equazione per determinare la velocità minima della connessione Internet: <*Impact number> / 0,3*.  

Supponiamo che il numero impatto sia *4,6875 Mbps.* Il calcolo per trovare la velocità minima di connessione a Internet sarà *di 4,6875 / 0,3 = 15,6*. In questo caso, la velocità della connessione Internet dovrebbe essere di *almeno 15,6 Mbps.*

Se Teams e Teams Telefono utilizzeranno più del 30% della velocità totale  della connessione Internet, il numero Impatto verrà visualizzato in rosso. In questo caso, potrebbe essere necessario aggiornare la connessione Internet.

![Avviso velocità della connessione.](../media/network-planner-report-speed-warning.png)

>[!NOTE]
> L'impatto della larghezza di banda fornito da Network Planner è solo una stima. È consigliabile usare [Call Quality Dashboard](../cqd-what-is-call-quality-dashboard.md) per monitorare attivamente l'esperienza utente per le chiamate audio e video Microsoft Teams all'interno dell'organizzazione.

## <a name="make-sure-the-computers-and-devices-on-your-network-can-reach-microsoft-365"></a>Assicurarsi che i computer e i dispositivi della rete possano raggiungere Microsoft 365

I computer e i dispositivi che usano Teams Telefono devono usare porte di rete specifiche per comunicare con Microsoft 365 servizi. Queste porte sono essenzialmente porte attraverso cui i dispositivi parlano tra loro tramite una rete o Internet. Il firewall deve consentire ai dispositivi della rete di raggiungere Microsoft 365 usando le porte di rete *in uscita* seguenti:

* **porte TCP** 80 e 443
* **Porte UDP** 3478, 3479, 3480 e 3481

Il modo più semplice per verificare se il firewall consente la comunicazione su queste porte di rete è eseguire un test di connettività usando lo strumento di connettività di rete Microsoft 365 dalla posizione [dell'ufficio che](/microsoft-365/enterprise/office-365-network-mac-perf-onboarding-tool) si vuole testare. Dopo aver completato il test, verificare i risultati e i suggerimenti.
