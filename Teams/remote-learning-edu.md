---
title: Risorse di Microsoft Teams per l'istruzione per amministratori
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Guida per l'apprendimento a distanza con Microsoft Teams per l'istruzione.
localization_priority: Priority
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: a2455a725822183d3e953993632a634a43002523
ms.sourcegitcommit: 0286eec17b7eea486b857a69fb6c6166ef0799d2
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 03/04/2020
ms.locfileid: "42408881"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Introduzione a Microsoft Teams per l'apprendimento a distanza

Microsoft Teams è una piattaforma che raggruppa al suo interno conversazioni, contenuti, attività e app. Creare classi per la collaborazione, mettere in contatto le community di studenti e di insegnanti: tutto in un unico luogo.

Segui le procedure consigliate in questo articolo per iniziare a usare Microsoft Teams per le tue esigenze formative e le funzionalità per l'apprendimento a distanza. Microsoft Teams può essere usato per creare classi in cui gli studenti possano interagire, fornendo una piattaforma per svolgere riunioni virtuali e assegnare attività. Gli amministratori e il personale scolastico possono tenersi aggiornati e collaborare usando Teams per inviare comunicazioni e confrontarsi. Gli insegnanti possono condividere materiale didattico nelle community di formazione professionale.

Microsoft Teams dispone di [client](get-clients.md) per PC (Windows, Mac e Linux), Web e dispositivi mobili (Android e iOS) per garantire che tutto il personale scolastico e gli studenti possano restare connessi.

Per altre informazioni sugli usi di Microsoft Teams, consultare i [webinar su Teams per l'istruzione](https://aka.ms/TeamsEDUWebinars).

## <a name="user-accounts-licenses-and-identity-security"></a>Account utente, licenze e sicurezza dell'identità

Microsoft Teams sfrutta le funzionalità di Microsoft 365 per l'autenticazione degli utenti e fornire servizi. È necessario creare identità per personale scolastico, insegnanti e studenti per facilitarne la collaborazione. Se le identità non esistono già, seguire questa procedura.

[Le licenze per Teams devono essere abilitate per gli utenti](user-access.md) prima che questi possano usare le funzionalità di Teams. Teams si basa su altre funzionalità di Microsoft 365, come [Gruppi di Office 365](Office-365-groups.md), [Exchange](Exchange-Teams-interact.md), [SharePoint e OneDrive](SharePoint-OneDrive-interact.md) per offrire possibilità di collaborazione. Se questi servizi sono abilitati, gli utenti avranno la migliore l'esperienza possibile di Teams. [Teams è supportato per gli utenti che hanno un account email su Google](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

## <a name="easily-set-up-microsoft-teams"></a>Come iniziare a usare Microsoft Teams

Ecco le due cose da fare per iniziare a usare Teams:

### <a name="1-allow-users-to-create-teams"></a>1. Consentire agli utenti di creare team

Gli studenti e gli insegnanti otterranno il massimo da Teams quando potranno usarlo con meno limitazioni possibili e personalizzarlo in base alle proprie necessità. In Teams, gli utenti possono personalizzare la loro esperienza d'uso creando team in grado di soddisfare le loro esigenze. **Per impostazione predefinita, tutti possono creare gruppi e team di Office 365**. A volte questa funzionalità potrebbe non essere desiderata. In questi casi, è possibile ad esempio impedire agli studenti di scuola primaria o secondaria inferiore di creare team. Se necessario, la possibilità di creare gruppi e team di Office 365 può essere [limitata a determinati gruppi di sicurezza](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups) all'interno dell'organizzazione.

I benefici per gli utenti di scuole secondarie superiori sono massimi quando tutti, inclusi gli studenti, possono creare team per le lezioni, le ricerche, i progetti e i gruppi di studio. Le scuole primarie e secondarie inferiori potrebbero voler impedire agli studenti di creare team per assicurarsi che tutte le comunicazioni fra studenti avvengano all'interno di un forum in cui è presente un adulto. In questo caso, la creazione di gruppi e team di Office 365 può essere limitata ai soli docenti e al personale scolastico.

### <a name="2-configure-user-experiences-using-policies"></a>2. Configurare le esperienze utente con i criteri

[I criteri di Teams](teams-policies.md) consentono di gestire le opzioni disponibili per utenti o gruppi di utenti specifici. I criteri possono essere applicati per definire a chi è consentito usare la chat privata, le chiamate private, la pianificazione delle riunioni, i tipi di contenuto che possono essere condivisi e molto altro ancora.

**Il personale di scuole secondarie, gli insegnanti e gli studenti** possono beneficiare delle funzionalità incluse nei criteri (globali) predefiniti. È possibile abilitare altre impostazioni dei criteri per aggiungere ulteriori funzionalità a Microsoft Teams, tra cui [le funzionalità di traduzione nei criteri di messaggistica](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings) e la trascrizione automatica delle riunioni nei criteri delle riunioni.

**Per gli studenti di scuola secondaria inferiore** può essere necessario limitare le funzionalità degli studenti. I criteri impostano limiti alle azioni che possono intraprendere gli studenti. Poiché in genere gli studenti sono il gruppo di utenti più numeroso e sono più spesso soggetti a impostazioni limitative, è consigliabile che le modifiche ai criteri per gli studenti siano rese "globali" (impostazione predefinita a livello di organizzazione).

Ecco una serie di configurazioni non predefinite di criteri che potrebbero essere assegnate a studenti di scuola primaria o secondaria inferiore per limitare le comunicazioni non moderate tra studenti:

#### <a name="messaging-policy"></a>Criteri di messaggistica

- Cambia in "disattivato"
- Classificazione contenuto Giphy impostato su "rigido"
- Traduzione messaggi impostato su "attivato"
- Invio di messaggi urgenti con le notifiche priorità impostato su "disattivato"
- Rimozione di utenti dalle chat di gruppo impostato su "disattivato"

#### <a name="meeting-policy"></a>Criteri per le riunioni

- Consenti riunione immediata nei canali impostato su "disattivato"
- Consenti componente aggiuntivo di Outlook impostato su "disattivato"
- Consenti pianificazione riunione di canale impostato su "disattivato"
- Consenti pianificazione di riunioni private impostato su "disattivato"
- Consenti riunione immediata in riunioni private impostato su "disattivato"

#### <a name="live-events-policy"></a>Criteri per gli eventi live

- Consenti pianificazione impostato su "disattivato"

#### <a name="calling-policy"></a>Criteri di chiamata

- Effettua chiamate private impostato su "disattivato"

#### <a name="teams-policy"></a>Criteri di team

- Creazione di canali privati impostato su "disattivato"

**Il personale e gli insegnanti di scuola primaria** dovrebbero disporre di criteri che gli garantiscano le funzionalità di base e che possano essere limitate per gli studenti. Creare nuovi criteri che consentano la pianificazione delle chat private e la pianificazione delle riunioni (le impostazioni predefinite per un nuovo criterio). [Assegnare questi criteri al personale e agli insegnanti tramite l'appartenenza al gruppo di sicurezza](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

## <a name="start-using-teams"></a>Introduzione a Teams

### <a name="create-class-teams-for-secure-classroom-use"></a>Creare team di classe per un uso sicuro delle classi

Microsoft Teams per l'istruzione offre [tipi di team specifici](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) per finalità didattiche. Il [tipo di team di classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) è progettato per le classi con funzionalità specifiche, tra cui: assegnazioni, un blocco appunti di OneNote per la classe, una [cartella di materiali](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) per proteggere il contenuto rendendolo di sola lettura per gli studenti e la possibilità di disattivare l'audio degli studenti che disturbano. Ci sono diversi modi per utilizzare i team di classe:

1. Il [School Data Sync](https://sds.microsoft.com/) (SDS) può essere **configurato da esperti IT** e consente di creare team di classe per tutte le classi sulla base delle informazioni contenute nel sistema informatico della scuola. Questo processo crea team per ciascuna sezione e mantiene sincronizzati gli elenchi di docenti e studenti. [Gli insegnanti potranno creare il team](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) prima di ammettere gli studenti al suo interno. Se invece un docente non usa il team, gli studenti non verranno ammessi nel team perché l'insegnante non fa clic su "attiva". SDS supporta oltre 80 diversi sistemi informatici scolastici (sistemi SIS) per l'importazione dei dati e il [team di supporto di SDS](https://aka.ms/SDSSupport) è a disposizione per assistere la scuola nella pianificazione e nella configurazione.
1. **Gli insegnanti impostano** il tipo di team di classe e invitano gli studenti. Gli insegnanti possono farlo [aggiungendo studenti al loro team](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), [condividendo un codice per unirsi al team](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f) oppure [condividendo un collegamento al team](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Se possibile, è consigliabile che siano gli insegnanti ad aggiungere gli studenti al team per assicurarsi che ricevano l'accesso e vengano informati di essere stati aggiunti a un team.

Dopo aver configurato il team, i proprietari del team possono [personalizzare le impostazioni del team](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158), tra cui aggiungere un'[immagine del team](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0), [creare canali](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US) per gli argomenti delle lezioni o spazi per i lavori di gruppo, [aggiungere un'app](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77) come Quizlet, Flipgrid o kahoot per ripassare contenuti didattici o [menzionare il team per il loro primo post](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2) e mandare una notifica a tutti per iniziare la conversazione.

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Creare team del personale per la comunicazione e la collaborazione

[I team del personale](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) sono progettati per gli amministratori e il personale scolastico per condividere facilmente informazioni e collaborare a iniziative scolastiche, ma anche per intraprendere azioni quali l'invio di comunicazioni, la configurazione di riunioni, la condivisione di contenuti e l'esecuzione di app esterne, come [Planner per la verifica delle attività](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2). Gli amministratori scolastici possono aggiungere membri del personale scolastico al team tramite la procedura guidata di creazione del team, [l'aggiunta di membri dopo la creazione del team](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9) o [la condivisione di un codice per unirsi al team o un collegamento al team](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). [Creare canali](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525) è un ottimo modo per organizzare le conversazioni e i file per sequenza di lavoro o materia. [La guida di riferimento per i proprietari dei team](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US) è il modo migliore per scoprire i doveri e le possibilità del proprietario del team.

## <a name="teams-meeting-scenarios"></a>Possibilità delle riunioni di Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Riunioni collaborative per le lezioni virtuali

[Le riunioni di Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams) supportano fino a 250 partecipanti contemporaneamente e possono avvalersi di audio, video, [condivisione di contenuti](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), lavagne e note condivise. Le riunioni possono essere programmate nel client Microsoft Teams come [riunioni in uno spazio privato o in un canale del team](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams), in modo che tutti i membri del team ne siano a conoscenza. Le riunioni possono essere registrate e salvate per essere riviste in un secondo momento dai partecipanti. Le registrazioni possono anche essere [trascritte per trovare facilmente i contenuti](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308) discussi. Per la riunione è possibile usare webcam, microfono e altoparlante di un portatile o di un telefono cellulare e ottenere un'elevata qualità audio/video da [dispositivi ottimizzati di Microsoft Teams](https://products.office.com/microsoft-teams/across-devices/devices).

### <a name="districtuniversity-events-or-updates"></a>Eventi o aggiornamenti distrettuali/universitari

In alcuni casi il pubblico è più grande e sono necessarie più funzionalità. In questi incontri intervengono relatori, produttori e moderatori delle sessioni di domande e risposte. Microsoft Teams supporta queste sessioni con [eventi live di Microsoft Teams](teams-live-events/what-are-teams-live-events.md). Gli eventi live possono essere usati ad esempio per aggiornamenti a livello di distretto o università, interventi delle autorità, per lezioni di grandi classi o gruppi di studenti oppure per coinvolgere l'intera community. Scopri di più su come gestire sessioni live in: [progettare e pianificare un evento live](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502), [produrre un evento live](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb), [partecipare a un evento live](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac) e [moderare una sessione di domande e risposte](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

## <a name="recommended-tips--tricks"></a>Suggerimenti e consigli

Per altre informazioni sull'uso di Microsoft Teams per l'istruzione, vedi: [Microsoft Teams per l'istruzione](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).

> [!NOTE]
> Alcune delle principali funzionalità di Microsoft Teams non sono specifiche per l'istruzione. Suggerimenti e consigli per le funzionalità di base di Teams sono disponibili in: [guida e formazione su Microsoft Teams](https://support.office.com/teams).

## <a name="adoption-content"></a>Contenuti di adozione

Microsoft ha sviluppato il [contenuto di adozione](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76) e le linee guida per l'impiego di Microsoft Teams. La [Guida all'adozione di Microsoft Teams](https://teamworktools.azurewebsites.net/tft/index.html) offre una panoramica del contenuto disponibile, mentre il [Microsoft Teams Customer Success Kit](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) contiene numerosi modelli utilizzabili per familiarizzare con Teams. Il Microsoft Education Center offre una formazione specifica su come vengono usati [Microsoft Teams](https://education.microsoft.com/learningPath/18793af1) e [OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) in classe.

Tra le risorse aggiuntive vi sono:

- [Video di suggerimenti rapidi "You Can in: 90"](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Playlist video di Microsoft Teams per l'istruzione](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [BLOG: scopri come questa scuola usa Teams per l'apprendimento a distanza](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>Prontezza del supporto

I professionisti IT e il personale di supporto possono aiutare a rendere l'architettura di Teams subito operativa, a mostrare le funzionalità di Microsoft 365 tramite i poster sull'architettura IT di Microsoft Teams e la formazione tecnica per amministratori.

Tra le altre risorse di supporto vi sono:

- [Risoluzione dei problemi di installazione e aggiornamento di Microsoft Teams](troubleshoot-installation.md)
- [Monitoraggio e gestione della qualità delle chiamate](monitor-call-quality-qos.md)
- [Verifica dell'integrità dei servizi per Teams](service-health.md)
- [Risorse di supporto per Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Monitoraggio e gestione della qualità delle chiamate](monitor-call-quality-qos.md)
- [Verifica dell'integrità dei servizi per Teams](service-health.md)
- [Risorse di supporto per Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Centro assistenza di Microsoft Teams](https://support.office.com/it-IT/teams)
