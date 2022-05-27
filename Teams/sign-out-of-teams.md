---
title: Disconnettersi da Microsoft Teams
author: SerdarSoysal
ms.author: serdars
manager: serdars
audience: Admin
ms.topic: article
ms.service: msteams
search.appverid: MET150
ms.reviewer: sbhatta
description: Informazioni su come disconnettersi da Microsoft Teams.
ms.custom: seo-marvel-apr2020
ms.localizationpriority: high
ms.collection:
- M365-collaboration
f1.keywords:
- NOCSH
appliesto:
- Microsoft Teams
ms.openlocfilehash: 80dd1d2561660c9dbbc72d902380c01fb198429e
ms.sourcegitcommit: cc6a3b30696bf5d254a3662d8d2b328cbb1fa9d1
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/25/2022
ms.locfileid: "65681957"
---
# <a name="sign-out-of-microsoft-teams"></a>Disconnettersi da Microsoft Teams

È consigliabile che gli utenti rimangano connessi all'app Microsoft Teams per continuare a ricevere chat, chiamate in arrivo e altre attività. A volte, gli utenti potrebbero voler disconnettersi dall'applicazione Teams per diversi motivi:

- Perché hanno finito di usare Teams per la giornata
- Vogliono usare un account diverso
- Perché condividono l’uso di un dispositivo con un'altra persona

Per questi ed altri motivi, Teams consente di disconnettersi dall'app e terminare la sessione.

## <a name="account-sharing-between-apps"></a>Condivisione dell'account tra app

I sistemi operativi moderni consentono la condivisione di account tra app diverse in un dispositivo. Questa progettazione single sign-on (SSO) consente agli utenti di usare più app sul dispositivo senza richiedere l'accesso a ogni singola app. Teams non controlla questo comportamento, ma sfrutta la comodità fornita da questa progettazione per l'esperienza dell'utente finale.

SSO ha un impatto importante sulla disconnessione. Quando gli utenti si disconnettono da Teams, i dati associati al loro account vengono rimossi dall'app Teams, ma altre app nel dispositivo potrebbero continuare ad avere accesso a quell’account. Ciò significa anche che agli utenti potrebbe non essere richiesto di immettere di nuovo le credenziali se scelgono di accedere di nuovo a Teams con lo stesso account.

## <a name="sign-out-of-teams-on-desktop"></a>Disconnettersi da Teams sul desktop

Per disconnettersi dal client desktop Teams o dal browser, selezionare l'immagine del profilo nella parte superiore dell'app e quindi scegliere **Disconnetti**.

Per l'app desktop, è anche possibile fare clic con il pulsante destro del mouse sull'icona dell'app sulla barra delle applicazioni e quindi scegliere **Disconnetti**.

Se sono stati aggiunti più account, è necessario disconnettersi da ogni singolo account. Dopo aver eseguito la connessione degli account in Teams, potrebbe essere necessario immettere di nuovo le credenziali al successivo avvio dell'app per accedere all'account.

## <a name="sign-out-of-teams-on-mobile-devices"></a>Disconnettersi da Teams nei dispositivi mobili

Nei dispositivi mobili, è possibile disconnettersi da Teams passando al menu, selezionando **Altro** e poi **Disconnetti**. Una volta disconnessi, sarà necessario reimmettere le credenziali per avviare l'app la volta successiva.

### <a name="global-sign-in-and-sign-out-for-frontline-workers"></a>Accesso e disconnessione globali per gli operatori sul campo

L'app Teams per Android ora supporta l'accesso e la disconnessione globali, in modo da fornire un'esperienza di accesso e disconnessione senza problemi per gli operatori sul campo. I dipendenti possono selezionare un dispositivo dal pool di dispositivi condivisi ed eseguire un singolo accesso per "renderlo loro" per tutta la durata del turno. Al termine del turno, potranno eseguire la disconnessione globale da tutti gli account nel dispositivo. Questa operazione consente di rimuovere tutte le informazioni personali e aziendali dal dispositivo, in modo che possa essere ripristinato nel pool di dispositivi. Per ottenere questa funzionalità, è necessario che il dispositivo sia in modalità condivisa.  Accertarsi di terminare qualsiasi riunione o chiamata attiva sul dispositivo prima di disconnettersi. Per informazioni su come configurare un dispositivo condiviso, vedere [Come usare la modalità dispositivo condiviso in Android](/azure/active-directory/develop/tutorial-v2-shared-device-mode#set-up-an-android-device-in-shared-mode).

## <a name="manual-cleanup"></a>Pulizia manuale

Anche se raramente, Teams potrebbe non eseguire la pulizia dopo la disconnessione completa. In base ai report degli utenti, le cause più comuni includono il blocco dei file da parte di un servizio in esecuzione nel sistema, ma potrebbero esserci altri motivi che dipendono dalle configurazioni o dai criteri di un singolo dispositivo e dalle autorizzazioni utente applicate al dispositivo.

Una delle cause comuni di questo problema è che Teams proverà a selezionare automaticamente un account esistente per l'accesso dell'utente. In situazioni come questa, l'utente potrebbe voler pulire manualmente la cache locale di Teams. Per altre informazioni, vedere [Accedere o rimuovere un account da Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US).

## <a name="related-topics"></a>Argomenti correlati

[Accedere o rimuovere un account da Teams](https://support.microsoft.com/office/sign-out-or-remove-an-account-from-teams-a6d76e69-e1dd-4bc4-8e5f-04ba48384487?ui=en-US&rs=en-US&ad=US)
