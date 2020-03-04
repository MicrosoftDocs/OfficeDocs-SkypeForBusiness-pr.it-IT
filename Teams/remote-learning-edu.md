---
title: Risorse di Microsoft teams per gli amministratori dell'istruzione
author: MicrosoftHeidi
ms.author: heidip
manager: serdars
ms.reviewer: karsmith
ms.topic: reference
ms.service: msteams
audience: admin
description: Guida all'avvio dell'apprendimento remoto per Microsoft teams per EDU.
localization_priority: Normal
search.appverid: MET150
f1.keywords:
- NOCSH
ms.collection:
- M365-collaboration
appliesto:
- Microsoft Teams
ms.openlocfilehash: 87d9e36578227c8f27acfdfd07abfa0cadbe69b7
ms.sourcegitcommit: f23c428043bb0b37c9a8600e64691bc2a1f2e874
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/03/2020
ms.locfileid: "42403838"
---
# <a name="get-started-with-microsoft-teams-for-remote-learning"></a>Introduzione a Microsoft teams per l'apprendimento remoto

Microsoft teams è una piattaforma che raggruppa le conversazioni, il contenuto, le assegnazioni e le app in un'unica posizione. Creare aule collaborative, connettersi a comunità di apprendimento professionali e connettersi con i colleghi, tutto da una singola esperienza.

Usare le procedure consigliate in questo articolo per iniziare a usare Microsoft teams per le esigenze didattiche per abilitare le funzionalità di apprendimento remoto. Microsoft teams può essere usato per abilitare la collaborazione in classe per coinvolgere gli studenti nelle conversazioni, fornendo una piattaforma di riunione virtuale e distribuendo le assegnazioni. Gli amministratori e il personale dell'Istituto di istruzione possono restare aggiornati e collaborare con team per gli annunci e le conversazioni topiche. Gli insegnanti possono condividere materiale didattico usando comunità di apprendimento professionali.

Microsoft teams dispone di [client](get-clients.md) disponibili per il desktop (Windows, Mac e Linux), Web e dispositivi mobili (Android e iOS) per assicurarsi che tutti i membri del personale e gli studenti possano rimanere connessi.

Altre informazioni sugli scenari di utilizzo di Microsoft teams in [Teams for Education Webinar Series](https://aka.ms/TeamsEDUWebinars).

## <a name="user-accounts-licenses-and-identity-security"></a>Account utente, licenze e sicurezza delle identità

Microsoft teams sfrutta le funzionalità Microsoft 365 per l'autenticazione degli utenti e la fornitura di servizi. Il personale, gli istruttori e gli studenti dovrebbero avere le identità stabilite per facilitare la collaborazione. Se le identità non esistono già, seguire questa procedura per stabilirle.

Le [licenze per i team devono essere abilitate per gli utenti prima di](user-access.md) poter iniziare a usare le funzionalità teams. Teams si basa sulle funzionalità aggiuntive di Microsoft 365, ad esempio [Office 365 groups](Office-365-groups.md), [Exchange](Exchange-Teams-interact.md), [SharePoint e OneDrive](SharePoint-OneDrive-interact.md) , per consentire scenari di collaborazione. Gli utenti ricevono l'esperienza teams migliore se sono abilitati anche tutti questi servizi. [Teams è supportato per gli utenti con posta elettronica ospitata da Google](https://docs.microsoft.com/microsoft-365/education/deploy/enabling-teams-for-education-for-google-users).

## <a name="easily-set-up-microsoft-teams"></a>Configurare facilmente Microsoft Teams

Queste sono le due operazioni che è necessario eseguire per iniziare a usare teams:

### <a name="1-allow-users-to-create-teams"></a>1. consentire agli utenti di creare Teams

Studenti ed insegnanti potranno sfruttare al meglio i team quando potranno usarlo con barriere minime e avere la flessibilità necessaria per adattarlo alle proprie esigenze. Un modo in cui gli utenti possono adattare l'esperienza dei team è la possibilità di creare team che soddisfino le proprie esigenze. **Per impostazione predefinita, tutti possono creare gruppi e team di Office 365**. In alcuni casi questa funzionalità potrebbe non essere appropriata; ad esempio, alcuni clienti potrebbero voler limitare gli studenti primari-secondari dalla creazione di team. Se necessario, il gruppo di Office 365 e la creazione del team possono essere [limitati a determinati gruppi di sicurezza](https://docs.microsoft.com/microsoft-365/admin/create-groups/manage-creation-of-groups) all'interno dell'ambiente.

I clienti dell'istruzione superiore beneficiano quando si consente a tutti, inclusi gli studenti, di creare team per classi, ricerche, progetti di gruppo e gruppi di studio. Le scuole primarie secondarie possono voler impedire agli studenti di creare team per assicurarsi che tutte le comunicazioni degli studenti a studenti avvengano in un forum che include un adulto. In questo caso, il gruppo di Office 365 e la creazione del team possono essere limitati a tutti gli insegnanti e il personale.

### <a name="2-configure-user-experiences-using-policies"></a>2. configurare le esperienze utente con i criteri

I criteri per i [Team](teams-policies.md) consentono di controllare le opzioni disponibili per utenti o gruppi di utenti specifici. I criteri possono essere applicati per definire chi deve essere autorizzato a usare la chat privata, le chiamate private, la pianificazione delle riunioni, i tipi di contenuto che possono essere condivisi e altro ancora.

Il **personale dell'istruzione superiore, gli educatori e gli studenti** traggono vantaggio dalle funzionalità incluse nei criteri predefiniti (globali). Alcune altre impostazioni dei criteri possono essere abilitate per aggiungere altre funzionalità a Microsoft teams, tra cui [l'abilitazione delle funzionalità di traduzione nei criteri di messaggistica](https://docs.microsoft.com/microsoftteams/messaging-policies-in-teams#messaging-policy-settings) e la trascrizione automatica delle riunioni nei criteri della riunione.

**Gli studenti delle scuole primarie secondarie** possono avere bisogno di funzionalità limitate fornite agli studenti. I criteri impostano i limiti per ciò che gli studenti possono fare. Poiché la popolazione studente è spesso il più grande insieme di utenti e spesso riceve le impostazioni più restrittive, si consiglia di apportare modifiche ai criteri degli studenti alle forze di polizia "globali (a livello di organizzazione)".

Ecco un set di configurazioni di criteri comuni non predefinite che verrebbero assegnate agli studenti primari-secondari per limitare le comunicazioni senza moderazione tra gli studenti:

#### <a name="messaging-policy"></a>Criteri di messaggistica

- Modifica impostato su "disattivato"
- Classificazione del contenuto Giphy impostata su "Strict"
- Tradurre i messaggi impostati su "attivato"
- Inviare messaggi urgenti con le notifiche prioritarie impostate su "disattivato"
- Rimuovere gli utenti dalle chat di gruppo impostate su "disattivato"

#### <a name="meeting-policy"></a>Criteri riunione

- Consenti riunione ora in canali impostati su "disattivato"
- Consentire il componente aggiuntivo Outlook impostato su "disattivato"
- Consentire la pianificazione della riunione canale su "disattivato"
- Consentire la pianificazione di riunioni private impostate su "disattivato"
- Consenti riunione ora in riunioni private impostate su "disattivato"

#### <a name="live-events-policy"></a>Criteri eventi dinamici

- Consenti pianificazione impostata su "disattivato"

#### <a name="calling-policy"></a>Criteri di chiamata

- Impostare le chiamate private su "disattivato"

#### <a name="teams-policy"></a>Criteri Teams

- Creare canali privati impostati su "disattivato"

I **membri del personale della scuola elementare e gli educatori** devono essere assegnati a criteri che concedono le funzionalità principali che possono essere limitate per gli studenti. Creare nuovi criteri che consentano la pianificazione della chat privata e della riunione (le impostazioni predefinite per un nuovo criterio). [Assegnare questi criteri al personale e agli insegnanti tramite l'appartenenza al gruppo di sicurezza](https://docs.microsoft.com/microsoftteams/assign-policies#assign-a-policy-to-a-group).

## <a name="start-using-teams"></a>Iniziare a usare Teams

### <a name="create-class-teams-for-secure-classroom-use"></a>Creare team di classe per un uso sicuro delle aule

Microsoft teams for Education offre [tipi di team specifici](https://support.office.com/article/choose-a-team-type-to-collaborate-in-microsoft-teams-0a971053-d640-4555-9fd7-f785c2b99e67) per l'uso didattico. Il [tipo di team di classe](https://support.office.com/article/create-a-class-team-in-microsoft-teams-fae422eb-58b7-4431-9ff2-a4b9b6ae7c5b) è progettato per le aule con caratteristiche specifiche, tra cui: assegnazioni, un blocco appunti di OneNote in aula, una [cartella materiali di classe](https://support.office.com/article/Use-folders-to-create-read-only-files-for-students-or-other-team-members-0e7791d7-8c9c-4749-9bca-984289477988) per proteggere il contenuto di sola lettura per gli studenti e la possibilità di disattivare l'audio degli studenti di disturbo. Ci sono un paio di modi in cui è possibile distribuire un team di classe:

1. La funzione [School Data Sync](https://sds.microsoft.com/) (SDS) può essere impostata **da essa**, consentendo la creazione di team di classe per tutte le classi in base alle informazioni nel sistema informativo scolastico. Questo processo prevede il provisioning di team per ogni sezione e la sincronizzazione dei ruoli di istruttore e studenti. Gli [insegnanti avranno la possibilità di preparare il loro team prima di](https://support.office.com/article/activate-early-access-class-teams-created-with-school-data-sync-0d154696-66ab-4fcf-b22f-c3d9a82aaf78) ammettere gli studenti. In alternativa, se un educatore non usa il team, gli studenti non saranno ammessi nel team perché l'educatore non fa mai clic su "attiva". SDS supporta oltre 80 diversi sistemi informativi scolastici (sistemi SIS) per l'importazione di dati e il [team di supporto SDS](https://aka.ms/SDSSupport) è pronto per assisterti nella pianificazione e configurazione.
1. Gli **educatori configurano** il proprio team di tipo classe e invitano studenti. Gli insegnanti possono eseguire questa operazione tramite [l'aggiunta di studenti al team](https://support.office.com/article/add-a-student-to-a-class-team-b88263bb-ace1-4702-8a48-f8a2cf4af954), la [condivisione di un codice di join](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f)o la [condivisione di un collegamento al team](https://support.office.com/article/Create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). Se possibile, è preferibile che gli insegnanti aggiungano gli studenti al team per assicurarsi che gli studenti accedano e vengano avvisati che sono stati aggiunti a un team.

Dopo la configurazione del team, i proprietari del team possono [personalizzare le impostazioni del team](https://support.office.com/article/find-your-class-team-s-settings-in-microsoft-teams-2592d4de-581d-4952-9028-02317880c158) , tra cui l'aggiunta di un' [immagine del team](https://support.office.com/article/change-your-team-picture-02ea2af6-b49d-4de8-9551-1a5e472993c0), la [creazione di canali](https://support.office.com/article/create-student-project-groups-channels-in-microsoft-teams-f85b3c07-fb87-4b94-883b-9be55f4b1e45?ui=en-US&rs=en-US&ad=US) per gli argomenti di classe o le aree di collaborazione di gruppo, [aggiungere un'app](https://support.office.com/article/add-an-app-to-teams-b2217706-f7ed-4e64-8e96-c413afd02f77) come Quizlet/Flipgrid/kahoot per la superficie di contenuti didattici esistenti e [menzionare il loro team per il primo post](https://support.office.com/article/using-the-conversation-tab-in-microsoft-teams-53d1c530-3797-4a6f-9892-6760f8763df2) per informare tutti e iniziare

### <a name="create-staff-teams-for-staff-communication-and-collaboration"></a>Creare team per la comunicazione e la collaborazione del personale

I [team di tipo staff](https://support.office.com/article/create-a-staff-team-in-microsoft-teams-314ac9d5-36a9-408e-8ae4-7ef20e9f1ddf) sono progettati per gli amministratori e il personale scolastico per condividere facilmente informazioni e collaborare a iniziative a livello scolastico, tra cui la creazione di annunci, le impostazioni delle riunioni, la condivisione di contenuti e l'introduzione di app esterne, come [Planner per il monitoraggio delle attività](https://support.office.com/article/create-a-plan-with-planner-d000976a-7490-4ddf-b9af-09ee764891e2). Gli amministratori dell'Istituto di istruzione possono aggiungere membri del personale scolastico al team tramite la creazione guidata team, [aggiungendo membri dopo aver creato il team](https://support.office.com/article/add-members-to-a-team-in-teams-aff2249d-b456-4bc3-81e7-52327b6b38e9)oppure [condividendo un codice di join o un collegamento al team](https://support.office.com/article/create-a-link-or-a-code-for-joining-a-team-11b0de3b-9288-4cb4-bc49-795e7028296f). La [creazione di canali](https://support.office.com/article/create-a-channel-in-teams-fda0b75e-5b90-4fb8-8857-7e102b014525) è un ottimo modo per organizzare conversazioni e file da workstream o subject. [La Guida di go-to per i proprietari del team](https://support.office.com/article/go-to-guide-for-team-owners-75f9669b-bd8f-457d-b60b-ac2ac9c8ead4?ui=en-US&rs=en-US&ad=US) è un ottimo posto per conoscere le funzioni e le funzionalità del proprietario del team.

## <a name="teams-meeting-scenarios"></a>Scenari di riunione Teams

### <a name="collaborative-meetings-for-virtual-classes"></a>Riunioni collaborative per classi virtuali

Le [riunioni di Microsoft teams](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams) supportano fino a 250 partecipanti concorrenti, inclusa la possibilità di avere audio, video, [condivisione di contenuti](https://support.office.com/article/show-your-screen-during-a-meeting-90c84e5a-b6fe-4ed4-9687-5923d230d3a7), lavagne e note condivise. Le riunioni possono essere pianificate all'interno del client Microsoft teams per la [riunione in uno spazio privato o in un canale del team](https://docs.microsoft.com/MicrosoftTeams/tutorial-meetings-in-teams), in modo che tutti i membri del team ne siano a conoscenza. Le riunioni possono essere registrate e salvate per i partecipanti per la revisione in un secondo momento. Queste registrazioni possono anche essere [trascritte per trovare facilmente contenuti](https://support.office.com/article/Microsoft-Stream-automatically-creates-closed-captions-for-videos-8d6ac353-9ff2-4e2b-bca1-329499455308) discussi. Per le riunioni è possibile usare una webcam, un microfono e un altoparlante per il portatile o un telefono cellulare e si può ottenere una qualità audio/video Premium dai [dispositivi Microsoft teams optimized](https://products.office.com/microsoft-teams/across-devices/devices).

### <a name="districtuniversity-events-or-updates"></a>Eventi o aggiornamenti di distretto/Università

Alcune istruzioni necessitano di un pubblico più ampio e altre funzionalità di produzione. Queste riunioni hanno spesso definito relatori, produttori e moderato Q&A. Microsoft teams supporta queste sessioni con [gli eventi live di Microsoft teams](teams-live-events/what-are-teams-live-events.md). Gli eventi dinamici possono essere usati per scenari, ad esempio aggiornamenti a livello distrettuale o universitario, indirizzi di leadership e istruzioni per le grandi classi o gruppi di studenti oppure estendersi alla community. Leggi altre informazioni su come eseguire sessioni Live in: [pianificare e pianificare un evento Live](https://support.office.com/article/video-plan-and-schedule-a-live-event-f92363a0-6d98-46d2-bdd9-f2248075e502), [produrre un evento](https://support.office.com/article/video-produce-a-live-event-34c89e79-ffd4-4a6a-baf6-77055e0709cb)Live, [partecipare a un evento Live](https://support.office.com/article/video-attend-a-live-event-d837ad8d-ce34-44d0-9744-9beb50e943ac)e [moderare una Q&a](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76).

## <a name="recommended-tips--tricks"></a>Suggerimenti & trucchi consigliati

Per altre informazioni sul modo in cui Microsoft teams viene usato per l'istruzione, [Microsoft teams per l'istruzione](https://support.office.com/article/Teams-5aa4431a-8a3c-4aa5-87a6-b6401abea114).

> [!NOTE]
> Alcune caratteristiche chiave di Microsoft teams non sono specifiche per l'istruzione. Consigli e suggerimenti per le funzionalità di base di teams sono disponibili all'indirizzo: [Guida e apprendimento di Microsoft teams](https://support.office.com/teams).

## <a name="adoption-content"></a>Contenuto adoption

Microsoft ha sviluppato linee guida per il contenuto e la strategia di [adozione](https://support.office.com/article/video-moderating-a-q-a-4984e582-8c66-4ea3-aaaf-d93cf62e1b76) per la distribuzione di Microsoft teams. La [Guida all'adozione di Microsoft teams](https://teamworktools.azurewebsites.net/tft/index.html) offre una buona panoramica del contenuto disponibile e il kit per il [successo del cliente teams](https://download.microsoft.com/download/A/E/9/AE984CD4-CF4B-41E7-9ABD-6735E3F01897/MicrosoftTeamsCustomerSuccessKit.zip) offre numerosi modelli che possono essere usati per sensibilizzare i team. Microsoft Educator Center offre formazione specifica per l'istruzione sul modo in cui [Microsoft teams](https://education.microsoft.com/learningPath/18793af1) e [OneNote](https://education.microsoft.com/learningPath/b6e3b5f2) vengono usati in classe.

Altre risorse di adozioni includono:

- ["È possibile in: 90" video di suggerimento rapido](https://www.youtube.com/playlist?list=PLiluTszfwwMKx-yVe7ekBX6gsLIHf1Z8k)
- [Playlist video di Microsoft teams for Education](https://www.youtube.com/playlist?list=PLiluTszfwwMKicAo6agloFALEB5WvYNYs)
- [BLOG: vedere come questa scuola usa team per l'apprendimento a distanza](https://www.wellingtoncollege.cn/tianjin-international/teaching-and-learning-update/)

## <a name="support-readiness"></a>Supporto della conformità

I professionisti IT e il personale di supporto possono essere aggiornati con l'architettura dei team e con l'uso sottostante delle funzionalità di Microsoft 365 con i poster di Microsoft teams Architecture IT e l'addestramento tecnico per gli amministratori.

Altre risorse di supporto includono:

- [Risolvere i problemi di installazione e aggiornamento di Microsoft Teams](troubleshoot-installation.md)
- [Monitorare e gestire la qualità delle chiamate](monitor-call-quality-qos.md)
- [Verificare l'integrità dei servizi per Teams](service-health.md)
- [Risorse di supporto per Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Monitorare e gestire la qualità delle chiamate](monitor-call-quality-qos.md)
- [Verificare l'integrità dei servizi per Teams](service-health.md)
- [Risorse di supporto per Teams](https://docs.microsoft.com/microsoft-365/admin/contact-support-for-business-products)
- [Centro assistenza di Microsoft Teams](https://support.office.com/en-us/teams)
