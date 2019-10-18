---
title: Usare Office 365 e connettori personalizzati in Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.date: 09/25/2017
ms.topic: article
ms.service: msteams
audience: admin
ms.collection:
- M365-collaboration
ms.reviewer: lucarras
search.appverid: MET150
description: I connettori mantengono il team aggiornato fornendo contenuti e aggiornamenti dai servizi usati di frequente direttamente in un canale.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 4b1dc57bbe3d216ee779f962ef4b2fc1152e2161
ms.sourcegitcommit: 0dcd078947a455a388729fd50c7a939dd93b0b61
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/17/2019
ms.locfileid: "37569841"
---
<a name="use-office-365-and-custom-connectors-in-microsoft-teams"></a>Usare Office 365 e connettori personalizzati in Microsoft Teams
=======================================================

I connettori mantengono la corrente del team consegnando i contenuti e gli aggiornamenti del servizio usati di frequente direttamente in un canale. Con i connettori, gli utenti di Microsoft teams possono ricevere gli aggiornamenti da servizi popolari come Twitter, Trello, Wunderlist, GitHub e Azure DevOps Services all'interno del flusso di chat del proprio team.

Qualsiasi membro di un team può connettere il proprio team ai servizi cloud più diffusi con i connettori se le autorizzazioni del team lo consentono e tutti i membri del team ricevono notifiche di attività da tale servizio. I connettori continueranno a funzionare anche dopo che il membro che ha inizialmente configurato il connettore ha lasciato. Qualsiasi membro del team con le autorizzazioni per Add\Remove può modificare la configurazione dei connettori da parte di altri membri.

I connettori di Office 365 possono essere usati sia con Microsoft teams che con i gruppi di Office 365, semplificando la sincronizzazione e la ricezione rapida delle informazioni rilevanti per tutti i membri. Sia Microsoft teams che Exchange usano lo stesso modello di connettore, che consente di usare gli stessi connettori in entrambe le piattaforme. È tuttavia importante notare che la disabilitazione dei connettori per il gruppo di Office 365 a cui un team dipende sarà in grado di disabilitare la possibilità di creare connettori anche per il team.

<a name="add-a-connector-to-a-channel"></a>Aggiungere un connettore a un canale
----------------------------

Attualmente è possibile aggiungere connettori usando i client desktop e Web di Microsoft teams. Tuttavia, le informazioni pubblicate da questi connettori possono essere visualizzate in **tutti i client** , inclusi i dispositivi mobili.

1. Per aggiungere un connettore a un canale, fare clic sui puntini di sospensione **(...),** a destra di un nome di canale, quindi fare clic su **connettori**.

    ![Screenshot dell'interfaccia teams con l'opzione Connectors selezionata.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image1.png)

2. È possibile selezionare una varietà di connettori disponibili e quindi fare clic su **Aggiungi**.

    ![Screenshot della finestra di dialogo connettori che mostra i connettori disponibili.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image2.png)

3. Immettere le informazioni necessarie del connettore selezionato e fare clic su **Salva**. Ogni connettore richiede il corretto funzionamento di un set di informazioni diverso e alcuni potrebbero richiedere l'accesso al servizio usando i collegamenti forniti nella pagina di configurazione del connettore.

    ![Screenshot della pagina di configurazione per il connettore RSS.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image3.png)

4. I dati forniti dal connettore vengono automaticamente inseriti nel canale.

    ![Screenshot dell'interfaccia teams che mostra una conversazione in un canale.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image4.png)

<a name="develop-custom-connectors"></a>Sviluppare connettori personalizzati
-----------------------------

È molto semplice sviluppare connettori personalizzati che possono essere integrati con le applicazioni line-of-business (LOB). Puoi usare il connettore **webhook in ingresso** incorporato per creare un endpoint per un canale che estrae i dati da qualsiasi applicazione usando i metodi post http.

1. Aggiungere il **webhook in arrivo** come qualsiasi altro connettore.

    ![Screenshot dell'opzione per aggiungere il connettore webhook in arrivo.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image5.png)

2. Per creare un hook, specificare un **nome**, aggiornare l'immagine di Webhook, se necessario, e fare clic su **Crea**.

    ![Screenshot della pagina di configurazione per il connettore del webhook in arrivo.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image6.png)

3. Le applicazioni che spingono i dati su questo canale richiedono l'URL del connettore webhook. Quando si crea il webhook viene creato un URL univoco. Condividere questo URL con gli sviluppatori in modo che possano configurare le proprie applicazioni per il push dei dati, in base alle esigenze.

    ![Screenshot dell'URL univoco del webhook.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image7.png)

4. Quando un'applicazione esterna inserisce i dati in un connettore, il messaggio viene visualizzato nell'elenco di conversazione del canale come messaggio speciale denominato messaggio della **scheda connettore** .

    ![Screenshot dell'interfaccia teams che mostra un messaggio di scheda connettore.](media/Use_Office_365_and_custom_connectors_in_Microsoft_Teams_image8.png)

     Gli sviluppatori possono configurare le proprie applicazioni per creare queste schede inviando una richiesta HTTP con un semplice payload JSON all'indirizzo webhook di un team, che è un URL univoco di tale endpoint fornito dalla procedura guidata. Fare in modo che gli sviluppatori facciano riferimento alla [Guida introduttiva ai connettori di Office 365 per Microsoft teams](https://docs.microsoft.com/en-us/microsoftteams/platform/concepts/connectors/connectors), nella rete Microsoft Developer Network, con istruzioni dettagliate e esempi di connettori. Altre risorse includono le [App Connect per i gruppi in Outlook](https://support.office.com/article/Connect-apps-to-your-groups-in-Outlook-ed0ce547-038f-4902-b9b3-9e518ae6fbab) e [Office Dev Center-Microsoft teams](https://go.microsoft.com/fwlink/?linkid=855784).
