---
title: Pianificare le conferenze telefoniche con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Riepilogo: leggere questo argomento per informazioni sulla pianificazione delle conferenze telefoniche con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: 04d0202e9d5187e33172e8bb4c4f1e51f5563d19
ms.sourcegitcommit: 556fffc96729150efcc04cd5d6069c402012421e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/26/2021
ms.locfileid: "58593560"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Pianificare le conferenze telefoniche con accesso esterno in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulla pianificazione delle conferenze telefoniche con accesso esterno in Skype for Business Server.
  
Le conferenze telefoniche con accesso esterno sono una funzionalità facoltativa di Skype for Business Server che consente ai partecipanti alla riunione di partecipare alla parte audio di una riunione chiamandoli da un telefono. Le conferenze telefoniche con accesso esterno sono un sottoinsieme delle funzionalità di audioconferenza e richiedono interventi di configurazione aggiuntive. In questo argomento vengono descritte le informazioni necessarie prima di distribuire le conferenze telefoniche con accesso esterno per l'organizzazione. 
  
Alcuni dei componenti necessari per le conferenze telefoniche con accesso esterno sono specifici per le conferenze telefoniche con accesso esterno e altri sono VoIP aziendale componenti. Sebbene le conferenze telefoniche con accesso esterno utilizzino alcuni degli stessi componenti utilizzati VoIP aziendale, è possibile distribuire le conferenze telefoniche con accesso esterno anche se non si distribuiscono VoIP aziendale. In questa sezione vengono descritti i componenti necessari per le conferenze telefoniche con accesso esterno. Per ulteriori informazioni sulla pianificazione di una soluzione VoIP aziendale completa, vedere [Plan your VoIP aziendale solution in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
Per le conferenze telefoniche con accesso esterno è necessario fornire connettività alla rete PSTN (Public Switched Telephone Network) distribuendo un Mediation Server. Oltre a distribuire un Mediation Server, è necessario considerare quanto segue per consentire le conferenze telefoniche con accesso esterno per l'organizzazione:
  
- Piano per la connessione alla rete PSTN (Public Switched Telephone Network)
    
- Piano per dial plan, numeri di accesso e aree conferenza
    
- Piano per la creazione di directory conferenze
    
- Criteri di conferenza per consentire l'accesso esterno
    
- Supporto per utenti aziendali e anonimi
    
> [!NOTE]
> Se si distribuiscono conferenze telefoniche con accesso esterno, è necessario distribuirla in ogni pool in cui si distribuiscono Skype for Business Server conferenza telefonica. Non è necessario assegnare numeri di accesso, i numeri che i partecipanti chiamano per partecipare a una conferenza, in ogni pool, ma è necessario distribuire la funzionalità di accesso esterno in ogni pool. Questo requisito supporta la funzionalità dei nomi registrati quando un utente chiama un numero di accesso da un pool per partecipare a Skype for Business Server conferenza in un pool diverso. 
  
## <a name="plan-for-pstn-connectivity"></a>Pianificare la connettività PSTN

Per le conferenze telefoniche con accesso esterno sono necessari almeno un Mediation Server e almeno un gateway PSTN (Public Switched Telephone Network). 
  
È possibile distribuire un Mediation Server in un sito centrale o in un sito di succursale. In un sito centrale è possibile collocare un Mediation Server in un pool Front End o un server edizione Standard oppure distribuirlo in un server o in un pool autonomo. In un sito di succursale è possibile distribuire un Mediation Server in un server autonomo o come componente del Survivable Branch Appliance.
  
È possibile distribuire un gateway PSTN in un sito centrale o in un sito di succursale. In un sito di succursale, il gateway PSTN può essere autonomo o un componente del Survivable Branch Appliance.
  
Per informazioni dettagliate sui requisiti di Mediation Server e gateway PSTN, vedere [Mediation Server component in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), Deploy a Mediation Server in [Topology Builder in Skype for Business Server e](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)Define a gateway in [Topology Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Pianificare dial plan, numeri di accesso e aree di conferenza

Per configurare le conferenze telefoniche con accesso esterno, è necessario creare dial plan e numeri di accesso alle conferenze telefoniche con accesso esterno. È inoltre possibile specificare le aree di accesso esterno che associano un numero di accesso alle conferenze telefoniche con accesso esterno ai relativi dial plan. Più precisamente:
  
- I dial plan sono set di regole di normalizzazione che specificano il numero e il modello di cifre in un numero di telefono e converte il numero di telefono nel formato standard E.164 necessario per il routing delle chiamate.
    
- I numeri di accesso alle conferenze telefoniche con accesso esterno sono i numeri che i partecipanti chiamano per partecipare a una conferenza.
    
- Ogni numero di accesso alle conferenze telefoniche con accesso esterno deve essere associato ad almeno un dial plan. 
    
- Ogni dial plan è associato a un'area di conferenza.
    
Quando si crea un dial plan, si specifica l'area di conferenza telefonica con accesso esterno applicabile al dial plan. Quando si crea il numero di accesso remoto, si selezionano le aree geografiche che associano il numero di accesso ai dial plan appropriati.
  
È inoltre possibile specificare l'ambito del dial plan: ambito utente, ambito pool o ambito sito. A ogni utente viene assegnato il dial plan dall'ambito più ristretto applicabile all'utente. Ad esempio, a un utente viene assegnato un dial plan a livello di utente, se applicabile. Se non si applica un dial plan a livello di utente, all'utente viene assegnato un dial plan a livello di pool. Se non si applica un dial plan a livello di pool, all'utente viene assegnato un dial plan a livello di sito. Se non si applica un dial plan a livello di sito, all'utente viene assegnato il dial plan globale. 
  
Prima di configurare i dial plan, è importante pianificare come si desidera assegnare un nome e utilizzare le aree geografiche. Le considerazioni seguenti si applicano alle aree di conferenza telefonica con accesso esterno:
  
- Un'area geografica è in genere un'area geografica associata a un ufficio o a un gruppo di uffici.
    
- Le lingue sono associate ai numeri di accesso esterno. Se si supportano aree geografiche con più lingue, è necessario decidere come definire le aree geografiche per supportare più lingue. Ad esempio, è possibile definire più aree geografiche in base a una combinazione di area geografica e lingua oppure definire una singola area geografica in base all'area geografica e disporre di numeri di accesso esterno diversi per ogni lingua.
    
- Quando un utente pianifica una riunione, per impostazione predefinita la riunione utilizza l'area specificata dal dial plan dell'utente.
    
- Per impostazione predefinita, tutti i numeri di accesso esterno per l'area geografica sono inclusi nell'invito alla riunione.
    
- È importante assegnare un nome alle aree in modo che siano chiaramente riconoscibili. L'utente può utilizzare i nomi delle aree geografiche per modificare l'area di una riunione in modo che nell'invito siano inclusi numeri di accesso diversi. Quando gli utenti usano Outlook per pianificare una riunione, l'utente utilizza il componente aggiuntivo per riunioni online per Skype for Business per modificare l'area geografica.
    
- Le aree geografiche devono essere progettate in modo che tutti gli invitati che desiderano accedere a una conferenza possano visualizzare un numero di accesso locale nell'invito alla conferenza.
    
- È possibile configurare l'ordine in cui i numeri di accesso all'interno di un'area vengono visualizzati nella pagina Impostazioni conferenza telefonica con accesso esterno (e, di conseguenza, l'ordine in cui vengono visualizzati nell'invito alla conferenza) utilizzando i cmdlet di Skype for Business Server Management Shell.
    
- Qualsiasi utente da qualsiasi località può chiamare qualsiasi numero di accesso remoto per partecipare a una conferenza.
    
Per ulteriori informazioni sulla creazione di un dial plan, vedere [Create or modify a dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) e Create or modify a [normalization rule in Skype for Business](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Pianificare le directory conferenze

Le directory conferenze mantengono un mapping tra l'ID riunione alfanumerico utilizzato da un partecipante per partecipare a una conferenza quando si utilizza Skype for Business e l'ID conferenza solo numerico utilizzato da un partecipante alla conferenza telefonica con accesso esterno per partecipare alla conferenza. Il formato dell'ID conferenza è il seguente:
  

\<housekeeping digit (1 digit)\>\<conference directory (usually 1-2 digits)\>\<conference number (variable number of digits\>\<check digit (1 digit)\>


La creazione di più directory conferenze garantisce che gli ID conferenza rimangano brevi fino a quando non viene creata una quantità significativa di conferenze. In un'organizzazione con un numero tipico di conferenze per utente, è consigliabile creare una directory conferenze per ogni 999 utenti del pool. Utilizzando questa linea guida, gli ID conferenza in genere possono essere mantenuti piccoli. Tuttavia, una volta che il numero di directory conferenze (tra i pool) supera 9, il numero ID conferenza crescerà per supportare conferenze aggiuntive.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Pianificare un criterio di conferenza che consenta l'accesso esterno

Le conferenze devono essere abilitate per l'accesso esterno quando si configurano i criteri di conferenza. Per impostazione predefinita, le conferenze abilitate per l'accesso esterno includono le informazioni seguenti nell'invito alla conferenza:
  
- ID conferenza numerico che identifica la conferenza
    
- Uno o più numeri di accesso PSTN
    
- Un collegamento a una pagina Impostazioni conferenza telefonica con accesso esterno, che contiene un elenco completo dei numeri di accesso con le lingue associate; un luogo in cui creare, reimpostare o sbloccare i numeri di identificazione personale (PIN); e altre informazioni, ad esempio i controlli DTMF (Dual Tone Multi-Frequency)
    
Per ulteriori informazioni sui criteri di conferenza, vedere [Configure dial-in conferencing in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) and Manage conferencing policies in [Skype for Business Server](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Supporto per utenti aziendali e anonimi

Le conferenze telefoniche con accesso esterno supportano utenti sia aziendali sia anonimi. Enterprise utenti dispongono di credenziali di Servizi di dominio Active Directory e Skype for Business Server account all'interno dell'organizzazione. Gli utenti anonimi non dispongono di credenziali aziendali all'interno dell'organizzazione. Nel contesto delle conferenze telefoniche con accesso esterno, un utente dell'organizzazione di un partner federato che utilizza la rete PSTN per connettersi a una conferenza viene trattato come un utente anonimo. Per le conferenze telefoniche con accesso esterno, diversamente da altri contesti, gli utenti federati non vengono autenticati.
  
Gli utenti aziendali o i coordinatori delle conferenze che partecipano a una conferenza abilitata per l'accesso esterno compongono uno dei numeri di accesso alla conferenza e devono immettere l'ID conferenza. Se un coordinatore non ha ancora eseguito l'accesso alla riunione, gli utenti possono immettere il proprio interno (o il numero di telefono completo) per le comunicazioni unificate e il PIN o attendere di essere ammessi da un coordinatore. Gli organizzatori della riunione possono partecipare alla riunione come coordinatori semplicemente immettendo il proprio PIN. Il Front End Server utilizza la combinazione di numero di telefono completo o interno e PIN per mappare in modo univoco gli utenti aziendali alle proprie credenziali di Active Directory. Di conseguenza, gli utenti aziendali vengono autenticati e identificati in base al nome nella conferenza. Gli utenti aziendali possono anche assumere un ruolo della conferenza predefinito dall'organizzatore.
  
> [!NOTE]
> Enterprise utenti che eseguono l'accesso da un telefono IP di office o da Skype for Business Server Attendant non viene richiesto il numero di telefono perché sono già autenticati. 
  
Gli utenti anonimi che desiderano partecipare a una conferenza telefonica con accesso esterno compongono uno dei numeri di accesso alla conferenza e devono quindi immettere il proprio ID conferenza. Gli utenti anonimi non autenticati devono inoltre registrare il proprio nome. Il nome registrato identifica gli utenti non autenticati nella conferenza. Gli utenti anonimi non vengono ammessi alla conferenza fino a quando un responsabile o un utente autenticato non accede, e non possono ricevere un ruolo predefinito.
  
> [!NOTE]
> Gli utenti aziendali che scelgono di non immettere il proprio numero di telefono e il PIN non vengono autenticati e pertanto devono registrare il proprio nome e vengono considerati utenti anonimi nella conferenza. 
  
Durante la pianificazione di una riunione, l'organizzatore della riunione può scegliere di limitare l'accesso alla riunione rendendo la riunione chiusa o bloccata. In questo caso, agli utenti con accesso remoto viene richiesto di eseguire l'autenticazione. 
  
- Se gli utenti con accesso remoto non riescono o scelgono di non eseguire l'autenticazione, vengono trasferiti nella sala di attesa in cui non vengono accettati o rifiutati da un responsabile oppure fino a quando non si verifica un timeout e non vengono disconnessi.
    
- Dopo l'ammissione a una conferenza, gli utenti con accesso remoto possono partecipare alla parte audio della conferenza e possono eseguire comandi DTMF (Dual-Tone Multi-Frequency) utilizzando la tastiera del telefono.
    
- I responsabili dell'accesso esterno possono esercitare comandi DTMF per attivare o disattivare l'audio dei partecipanti, bloccare o sbloccare la conferenza, ammettere persone dalla sala di attesa e attivare o disattivare gli annunci di ingresso e uscita.
    
- I dirigenti possono anche usare un comando DTMF per ammettere tutti gli utenti dalla sala di attesa, che modifica le autorizzazioni della riunione per consentire a chiunque si unirà successivamente. 
    
- Tutti i partecipanti all'accesso esterno possono esercitare comandi DTMF per ascoltare la Guida, ascoltare l'elenco conferenze e disattivare l'audio.
    
- I partecipanti con accesso esterno, ovvero se estendono o meno la chiamata dalla rete PSTN, ascoltano gli annunci personali durante la conferenza, ad esempio se sono stati disattivati o disattivati, se la riunione è stata registrata o se qualcuno è in attesa nella sala di attesa.
    
    > [!NOTE]
    > I partecipanti che accedono alla conferenza facendo clic su un collegamento invece di comporre un numero non possono ascoltare gli annunci personali. 
  

