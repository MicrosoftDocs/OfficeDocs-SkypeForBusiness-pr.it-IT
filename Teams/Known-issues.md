---
title: Problemi noti di Microsoft Teams
author: LolaJacobsen
ms.author: lolaj
manager: serdars
ms.topic: troubleshooting
ms.service: msteams
ms.collection:
- Teams_ITAdmin_GuestAccess
- M365-collaboration
ms.custom: seo-marvel-mar2020
ms.reviewer: marcl
audience: admin
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
description: Usare questo elenco di problemi noti per l'app client Microsoft Teams e l'esperienza di amministrazione per risolvere i problemi all'interno dell'organizzazione.
appliesto:
- Microsoft Teams
ms.openlocfilehash: 1343317d29f196caf151ead5a6429fb3edf19d87
ms.sourcegitcommit: a9e16aa3539103f3618427ffc7ebbda6919b5176
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2020
ms.locfileid: "43902301"
---
# <a name="known-issues-for-microsoft-teams"></a>Problemi noti di Microsoft Teams

Questo articolo elenca i problemi noti di Microsoft Teams per area funzionale.

## <a name="common-issues-and-resolutions"></a>Problemi noti e risoluzioni

> [!NOTE]
> Se serve aiuto per distribuire Teams a supporto dei lavoratori a seguito dell'epidemia di COVID-19, vedere [Supporto per i lavoratori remoti con Teams](support-remote-work-with-teams.md). Inoltre, si potrebbe essere idonei per l'assistenza alla distribuzione nell'ambito del programma Microsoft 365 FastTrack. Visitare [FastTrack Center](https://www.microsoft.com/fasttrack) per inviare una richiesta.

### <a name="for-all-teams-customers"></a>Per tutti i clienti di Teams

| |  |
|---------|---------|
|**Nuovi utenti di Teams?**    |Vedere [Introduzione a Microsoft Teams](get-started-with-teams-quick-start.md).         |
|**Abilitare l'accesso guest a Teams**     |Esaminare l'[Elenco di controllo per l'accesso guest in Teams](guest-access-checklist.md) e verificare che siano stati completati tutti i passaggi. Consultare le seguenti risorse aggiuntive:<ul><li>[Informazioni sull'accesso guest a Microsoft Teams](guest-access.md)</li>[Come un guest partecipa a un team](guest-joins.md) <li>[Configurazione - Elenco di controllo per l'accesso guest a Microsoft Teams](guest-access-checklist.md)</li></ul>|
|**Riunioni e chiamate in ingresso di Teams**    |Serve aiuto per attivare o configurare l'audioconferenza in Teams? L'utente è stato creato di recente? In questo caso, sarà necessario attendere da 2 a 24 ore **perché le impostazioni abbiano effetto**.<br>Per verificare che l'utente disponga della licenza per Audioconferenza e di un numero a pagamento predefinito:<br><ol><li>Nell'interfaccia di amministrazione di Microsoft 365, passare a **Utenti attivi** e quindi selezionare l’utente in questione.</li><li> A seconda della versione dell'interfaccia di amministrazione, scegliere **Licenze e app** o fare clic su **Modifica** in **Licenze dei prodotti**.</li><li> Verificare che per l'utente siano selezionate le licenze per Audioconferenza, Microsoft Teams e Skype for Business Online (Piano 2).</li><li>In **Interfacce di amministrazione** fare clic su **Mostra tutto** e poi su **Teams**.</li><li>Nell'interfaccia di amministrazione di Microsoft Teams fare clic su **Portale legacy**.</li><li>Nell'interfaccia di amministrazione di Skype for Business fare clic su **Audioconferenza** e poi su **Utenti**.</li><li>Selezionare l'utente in questione e verificare che disponga di un numero a pagamento predefinito.</li> </ol> Per altre informazioni, vedere [Piani per chiamate per Office 365](calling-plans-for-office-365.md) o chiamare il team Microsoft Commerce Billing per ricevere assistenza con domande relative alla gestione delle licenze. <br><br>Risorse aggiuntive:<ul><li>[Riunioni e conferenze in Microsoft Teams](deploy-meetings-microsoft-teams-landing-page.md)</li><li>[Audioconferenza in Office 365](audio-conferencing-in-office-365.md)</li></ul>       |
|**Licenza di Teams Exploratory**     |L'esperienza Microsoft Teams Exploratory consente agli utenti dell'organizzazione che hanno Azure Active Directory (AAD) e non hanno una licenza per Teams di iniziare a usare un'esperienza esplorativa di Teams. Gli amministratori possono attivare o disattivare questa funzionalità per gli utenti nell'organizzazione. L'esperienza Teams Exploratory ha sostituito la precedente [Microsoft Commercial Cloud Trial](iw-trial-teams.md). <br><br>Risorse aggiuntive:<ul><li>[Come aderire all'esperienza Teams Exploratory](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Gestire l'esperienza Teams Exploratory](teams-exploratory.md#manage-the-teams-exploratory-experience)</li></ul>|
|**Canali privati**    |I canali privati di Microsoft Teams creano spazi dedicati per la collaborazione all'interno dei team. Solo gli utenti proprietari del team o membri del canale privato possono accedere al canale. Tutti gli utenti, inclusi gli utenti guest, possono essere aggiunti come membri a un canale privato, purché siano già membri del team.<br><br>È possibile usare un canale privato se si vuole limitare la collaborazione agli utenti che hanno la necessità acquisire competenze o se si vuole agevolare le comunicazioni tra un gruppo di persone assegnato a un progetto specifico, senza dover gestire un altro team.<br><br>Risorse aggiuntive:<ul><li>[Come aderire all'esperienza Teams Exploratory](teams-exploratory.md#how-users-sign-up-for-the-teams-exploratory-experience)</li><li>[Gestire l'esperienza Teams Exploratory](teams-exploratory.md#manage-the-teams-exploratory-experience)</li><ul>        |
|**Criteri riunione**|I [criteri riunione](meeting-policies-in-teams.md) vengono usati per controllare le funzionalità disponibili per i partecipanti alle riunioni programmate dagli utenti nell'organizzazione. Dopo aver creato un criterio e aver apportato le modifiche, è possibile assegnare gli utenti al criterio.         |
||**Cambiare o creare un criterio riunione**<br><br>Per modificare o creare un criterio riunione, passare all'interfaccia di amministrazione di Microsoft Teams > **Riunioni**  >  **Criteri riunione**. Selezionare un criterio dall'elenco o selezionare **Aggiungi**. Se si sta creando un nuovo criterio, aggiungere un nome e una descrizione. Il nome non può contenere caratteri speciali o più di 64 caratteri. Scegliere le impostazioni desiderate e poi fare clic su **Salva**. Ad esempio, si supponga di avere un gruppo di utenti e di voler limitare la larghezza di banda necessaria per la riunione. È possibile creare un nuovo criterio personalizzato denominato "Larghezza di banda limitata" e disabilitare le impostazioni seguenti:<br><br>In **Audio e video**:<ul><li>Disattivare Consenti registrazione cloud.</li><li>Disattivare Consenti video IP.</li></ul>In **Condivisione di contenuti**:<ul><li>Disabilitare la modalità di condivisione dello schermo.</li><li>Disattivare Consenti la lavagna.</li><li>Disattivare Consenti note condivise.</li></ul>Assegnare poi il criterio agli utenti.         |
| |**Assegnare un criterio riunione agli utenti**<br><br><ol><li>Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Utenti** e quindi fare clic sull'utente.</li><li>Per selezionare l'utente facendo clic a sinistra del nome utente e poi fare clic su **Impostazioni di modifica**.</li><li>In **Criteri riunioni** selezionare il criterio da assegnare e poi fare clic su **Applica**.</li></ol>Per assegnare un criterio a più utenti alla volta, vedere [modificare le impostazioni degli utenti di Teams in blocco](edit-user-settings-in-bulk.md). In alternativa è possibile eseguire le operazioni seguenti:<ol><li>Nel riquadro di spostamento sinistro dell'interfaccia di amministrazione di Microsoft Teams passare a **Riunioni > Criteri riunioni**.</li><li>Selezionare il criterio facendo clic a sinistra del nome del criterio.</li><li>Scegliere **Gestisci utenti**.</li><li>Nel riquadro **Gestisci utenti** cercare l'utente per nome visualizzato o in base al nome utente, selezionare il nome e poi fare clic su **Aggiungi**. Ripetere questa operazione per ogni utente da aggiungere.</li><li>Dopo avere aggiunto gli utenti, fare clic su **Salva**.</li>         |
|**Risolvere i problemi di assenza della tastiera del telefono**     |Eseguire le operazioni seguenti: <ul><li>Verificare che all'utente sia stata assegnata una [licenza di Teams](assign-teams-licenses.md).</li><li>Assicurarsi che all'utente sia stato assegnato un [piano di chiamata](calling-plan-landing-page.md).</li><li>Abilitare l’utente per [VoIP aziendale](https://docs.microsoft.com/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/enable-users-for-enterprise-voice-online-and-phone-system-voicemail#to-enable-your-users-for-phone-system-in-office-365-voice-and-voicemail).</li></ul>      |
|**Risolvere i problemi di accesso a Teams**   |Prima di tutto, verificare l'[integrità del servizio Microsoft Teams](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/servicehealth). Controllare quindi se sono presenti codici di errore comuni e vedere [Perché non riesco ad accedere a Microsoft Teams?](https://support.office.com/article/a02f683b-61a3-4008-9447-ee60c5593b0f)  Può anche essere necessario consultare [Modelli di identità e autenticazione in Microsoft Teams](identify-models-authentication.md).         |

### <a name="for-education-customers"></a>Per i clienti del settore dell'istruzione

|||
|---------|---------|
|Viene visualizzato il messaggio "Stai perdendo un'occasione!" .   |Assicurarsi di [Abilitare Microsoft Teams per l'istituto di istruzione](https://docs.microsoft.com/microsoft-365/education/intune-edu-trial/enable-microsoft-teams). Nei tenant EDU, Teams non è abilitato per impostazione predefinita. Per prima cosa è necessario attivarlo. <br><br>Vedere poi [Insegnamento e apprendimento remoto in Office 365 Education](https://support.office.com/article/remote-teaching-and-learning-in-office-365-education-f651ccae-7b65-478b-8366-51bb884025c4) per le indicazioni più aggiornate su come configurare l'istituto di istruzione, pianificare le lezioni, creare riunioni virtuali e condividere contenuti con gli studenti.<br><br>Infine, assicurarsi di consultare i video di formazione per amministratori IT di Microsoft Teams, le presentazioni e molto altro ancora qui: [Formazione amministratori per Teams](itadmin-readiness.md).        |

Vedere [Risoluzione dei problemi di Teams](https://docs.microsoft.com/MicrosoftTeams/troubleshoot/teams) per altre informazioni su come risolvere i problemi relativi a Microsoft Teams.
