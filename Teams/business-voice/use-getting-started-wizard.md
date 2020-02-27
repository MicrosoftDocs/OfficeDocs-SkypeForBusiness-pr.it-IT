---
title: Usare la procedura guidata Attività iniziali per configurare Business Voice
author: dstrome
ms.author: dstrome
manager: serdars
ms.topic: article
ms.service: msteams
audience: admin
f1.keywords:
- NOCSH
localization_priority: Priority
MS.collection:
- Teams_ITAdmin_Help
- M365-collaboration
- Teams_Business_Voice
search.appverid: MET150
description: ''
appliesto:
- Microsoft Teams
ms.openlocfilehash: ba381659572fa8cfda6ac605a2910ef19220dcbd
ms.sourcegitcommit: 29034bda30a8460eb18600785f785528d0944041
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 02/26/2020
ms.locfileid: "42285818"
---
# <a name="use-the-getting-started-wizard-to-set-up-business-voice"></a>Usare la procedura guidata Attività iniziali per configurare Business Voice

La procedura guidata Attività iniziali per configurare rapidamente Microsoft 365 Business Voice consente di effettuare e ricevere chiamate telefoniche in Microsoft Teams. Per le aziende di piccole dimensioni che partono da zero, la procedura guidata consente di iniziare a usare il sistema in pochi minuti con numeri di telefono, menu di chiamata, messaggi di saluto e altro ancora. Per le aziende più grandi con una soluzione di telefonia consolidata, la procedura guidata consente di configurare una distribuzione pilota di Business Voice, in modo da poterlo usare con pochi utenti prima di configurarlo per tutti. In entrambi i casi, si può iniziare a usare Business Voice appena terminata la procedura guidata.

È consigliabile leggere questo articolo prima di avviare la procedura guidata. Quando si è pronti a eseguire la procedura guidata, selezionare **Inizia** nella pagina [Introduzione a Microsoft 365 Business Voice](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/featureexplorer/apps/SmbVoice). Accedere con l'account usato per creare l'abbonamento o un altro account di amministratore globale.

> [!IMPORTANT]
> Business Voice è attualmente disponibile in Canada e nel Regno Unito. Altri paesi e aree geografiche diventeranno disponibili nel 2020.
>
> Microsoft Teams e Business Voice funzionano solo quando le cassette postali degli utenti si trovano in Microsoft 365.  Le cassette postali in Exchange Server locale non sono supportate.

<!-- After you've finished the wizard, you may want to check out the following articles:

* [Things to try with Business Voice](things-to-try.md)
* [Business Voice design customization](customize-business-voice.md)-->

Se non si vuole personalizzare subito nulla, l'operazione è completata. È possibile iniziare subito a usare Business Voice.

## <a name="emergency-services-location"></a>Ubicazione dei servizi di emergenza

<table>
    <tr>
        <td>Se si desidera modificare l'indirizzo di emergenza, fare clic su <b>Modifica</b> e immettere un nuovo indirizzo. L'indirizzo specificato viene convalidato per verificare che sia legittimo e formattato correttamente per i servizi di risposta alle emergenze. L'indirizzo viene quindi assegnato a tutti gli utenti a cui si assegnerà un numero nel passaggio successivo. Se si hanno dipendenti in più ubicazioni, vedere <a href="./customize-business-voice.md">Personalizzazione di Business Voice</a> per aggiungere e assegnare più indirizzi di emergenza dopo aver completato la procedura guidata Attività iniziali.</td> 
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400"></td></tr>
</table>

Per altre informazioni, vedere [Che cosa sono il routing delle chiamate, gli indirizzi e le posizioni per gli interventi di emergenza?](../what-are-emergency-locations-addresses-and-call-routing.md)

## <a name="company-phone-number"></a>Numero di telefono aziendale

<table>
    <tr>
        <td>Oltre a un nuovo numero di telefono locale, si può acquistare un numero verde o trasferire un numero esistente in Microsoft 365. Per configurare un numero verde, è necessario acquistare un piano per chiamate. Per trasferire uno o più numeri in Microsoft 365, accedere all'<a href="https://admin.teams.microsoft.com">interfaccia di amministrazione di Teams</a> al termine della procedura guidata.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-choose-number.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Se si trasferisce un numero di telefono esistente in Microsoft 365, nella procedura guidata verrà comunque visualizzato un numero di telefono temporaneo. Questo è il comportamento previsto. Dopo aver completato la procedura guidata e il processo di portabilità, il numero di telefono temporaneo verrà sostituito con il numero preesistente.

## <a name="user-licenses"></a>Licenze utente

<table>
    <tr>
        <td>Per assegnare le licenze agli utenti, selezionare le persone dell'organizzazione che vogliono effettuare o ricevere telefonate all'esterno di Teams (ad esempio, per chiamare un fornitore). È possibile assegnare solo le licenze di Business Voice già disponibili. Se ne servono di più, è possibile acquistare altre licenze al termine della procedura guidata.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-get-numbers.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Dopo aver completato la procedura guidata, è possibile trasferire i numeri di telefono esistenti in Microsoft 365. Dopo aver completato il processo di portabilità, i numeri di telefono trasferiti sostituiranno i numeri di telefono temporanei forniti dalla procedura guidata.

## <a name="incoming-call-greeting"></a>Messaggio di saluto per le chiamate in arrivo

<table>
    <tr>
        <td>È possibile caricare un file audio (MP3 o WAV) di dimensioni massime di 5 megabyte (MB) da usare come messaggio di saluto, oppure si può digitare il messaggio e Microsoft 365 userà la sintesi vocale per leggerlo al chiamante. Il messaggio di saluto sarà la prima cosa che sentirà chi chiama il numero di telefono dell'azienda. Per la sintesi vocale, potrebbe essere necessario usare grafie fonetiche per ottenere la pronuncia giusta.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-greeting.png" width="400">
        </td>
    </tr>
</table>

## <a name="call-menu-and-forwarding"></a>Menu di chiamata e inoltro di chiamata

<table>
    <tr>
        <td>È possibile inoltrare tutte le chiamate a un utente specifico oppure configurare un menu di chiamata da cui scegliere opzioni. Se si crea un menu di chiamata, vengono specificate le opzioni che un chiamante può selezionare premendo un numero sul tastierino del telefono o pronunciando l'opzione con un comando vocale. Ogni opzione di menu può inoltrare chiamate a un utente specifico.<br><br>
        Si può caricare un file audio (MP3 o WAV) fino a un massimo di 5 MB che fornisce istruzioni al chiamante oppure è possibile digitare le istruzioni. Microsoft 365 userà la sintesi vocale per leggere le istruzioni al chiamante. Per ottenere la pronuncia giusta potrebbe essere necessario scrivere le parole così come si pronunciano, usando un'ortografia errata.
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-call-forwarding-rules.png" width="400">
        </td>
    </tr>
</table>

> [!IMPORTANT]
> Le attività iniziali guidate consentono di configurare un semplice menu di chiamata per diventare subito operativi. Se si hanno più numeri di telefono con i menu di chiamata da configurare o se si vogliono configurare menu di chiamata più complessi (detti anche operatori automatici), vedere [Configurare un operatore automatico cloud](set-up-auto-attendants.md) al termine della procedura guidata.

<table>
    <tr>
        <td> <p>La procedura guidata Attività iniziali considera le informazioni immesse dall'utente e configura Business Voice. Nella pagina <b>Panoramica</b>, è possibile visualizzare i numeri di telefono assegnati agli utenti, esaminare il menu di chiamata, ascoltare il messaggio di saluto e altro ancora.</p>
             <p>La configurazione richiede alcuni minuti. Se si seleziona <b>Fine</b>, la configurazione di Business Voice continua in background. In alternativa, è possibile attendere il completamento della configurazione. Una volta completata la procedura, passare a <b>Voce </b>nell'<a href="https://admin.teams.microsoft.com" target="_blank">interfaccia di amministrazione di Teams</a> per configurare altre funzionalità di Business Voice.</p>
        </td>
        <td><img src="https://docs.microsoft.com/MicrosoftTeams/media/voice-wizard-finish-page.png" width="400">
        </td>
    </tr>
</table>
