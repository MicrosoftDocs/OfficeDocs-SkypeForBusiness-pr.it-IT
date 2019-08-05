---
title: Pianificare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
ms.reviewer: ''
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: ea024a26-37b3-410e-961b-83ab85c07540
description: 'Riepilogo: leggere questo argomento per informazioni sulla pianificazione per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.'
ms.openlocfilehash: e5c058f614ca7201815cb623d45fd28c18520b85
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36187844"
---
# <a name="plan-for-dial-in-conferencing-in-skype-for-business-server"></a>Pianificare i servizi di conferenza telefonica con accesso esterno in Skype for Business Server
 
**Riepilogo:** Leggere questo argomento per informazioni sulla pianificazione per i servizi di conferenza telefonica con accesso esterno in Skype for Business Server.
  
I servizi di conferenza telefonica con accesso esterno sono una caratteristica facoltativa di Skype for Business Server che consente ai partecipanti alla riunione di partecipare alla parte audio di una riunione chiamando la riunione da un telefono. Le conferenze telefoniche con accesso esterno sono un sottoinsieme di servizi di audioconferenza e richiedono una configurazione aggiuntiva. Questo argomento descrive le informazioni utili prima di distribuire i servizi di conferenza telefonica con accesso esterno per l'organizzazione. 
  
Alcuni dei componenti necessari per i servizi di conferenza telefonica con accesso esterno sono specifici per i servizi di conferenza telefonica con accesso esterno e alcuni componenti di VoIP aziendale. Anche se i servizi di conferenza telefonica con accesso esterno usano alcuni degli stessi componenti usati da Enterprise Voice, è possibile distribuire i servizi di conferenza telefonica con accesso esterno anche se non si distribuisce VoIP aziendale. In questa sezione vengono descritti i componenti necessari per i servizi di conferenza telefonica con accesso esterno. Per altre informazioni sulla pianificazione di una soluzione VoIP aziendale completa, vedere [pianificare la soluzione VoIP aziendale in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/enterprise-voice-solution.md).
  
I servizi di conferenza telefonica con accesso esterno richiedono la connettività alla rete PSTN (Public Switched Telephone Network) distribuendo un Mediation Server. Oltre alla distribuzione di un Mediation Server, è necessario tenere presente quanto segue per consentire i servizi di conferenza telefonica con accesso esterno per l'organizzazione:
  
- Piano per la connessione alla rete PSTN (Public Switched Telephone Network)
    
- Piano per i dial plan, i numeri di accesso e le aree di conferenza
    
- Piano per la creazione di directory di conferenza
    
- Criteri di conferenza per consentire l'accesso esterno
    
- Supporto per utenti aziendali e anonimi
    
> [!NOTE]
> Se si distribuiscono i servizi di conferenza telefonica con accesso esterno, è necessario distribuirla in tutti i pool in cui si distribuiscono le conferenze di Skype for Business Server. Non è necessario assegnare i numeri di accesso: i partecipanti al numero chiamano per partecipare a una conferenza, in ogni pool, ma è necessario distribuire la funzionalità chiamata in ingresso in ogni pool. Questo requisito supporta la caratteristica nome registrato quando un utente chiama un numero di accesso da un pool per partecipare a una conferenza di Skype for Business Server in un pool diverso. 
  
## <a name="plan-for-pstn-connectivity"></a>Pianificazione per la connettività PSTN

I servizi di conferenza telefonica con accesso esterno richiedono almeno un server di mediazione e almeno un gateway PSTN (Public Switched Telephone Network). 
  
È possibile distribuire un Mediation Server in un sito centrale o in un sito di succursale. In un sito centrale è possibile collocare un Mediation Server in un pool Front-end o in un server Standard Edition oppure distribuirlo in un server o un pool autonomo. In un sito di succursale è possibile distribuire un Mediation Server in un server autonomo o come componente di Survivable Branch Appliance.
  
È possibile distribuire un gateway PSTN in un sito centrale o in un sito di succursale. In un sito di succursale il gateway PSTN può essere autonomo o un componente dell'appliance Survivable Branch.
  
Per informazioni dettagliate sui requisiti di Mediation Server e gateway PSTN, vedere [Componente Mediation Server in Skype for Business Server](../../plan-your-deployment/enterprise-voice-solution/mediation-server.md), [distribuire un Mediation Server in Generatore di topologie in Skype for Business Server](../../deploy/deploy-enterprise-voice/deploy-a-mediation-server.md)e [definire un gateway in topologia Builder in Skype for Business Server](../../deploy/deploy-enterprise-voice/define-a-gateway.md).
  
## <a name="plan-for-dial-plans-access-numbers-and-conferencing-regions"></a>Pianificare piani di chiamata, numeri di accesso e aree di conferenza

Per configurare i servizi di conferenza telefonica con accesso esterno, è possibile creare numeri di dial plan e servizi di conferenza telefonica con chiamata in ingresso. Puoi anche specificare le aree di accesso esterno che associano un numero di telefono per i servizi di conferenza telefonica con chiamata in ingresso con i relativi dial plan. In modo più specifico:
  
- I dial plan sono insiemi di regole di normalizzazione che specificano il numero e il modello di cifre in un numero di telefono e traducono il numero di telefono nel formato standard E. 164 necessario per il routing delle chiamate.
    
- I numeri di accesso per i servizi di conferenza telefonica con chiamata in ingresso sono i numeri che partecipano a una conferenza.
    
- Tutte le conferenze telefoniche con accesso esterno devono essere associate ad almeno un dial plan. 
    
- Ogni dial plan è associato a un'area conferenze.
    
Quando si crea un dial plan, si specifica l'area di conferenza telefonica con accesso esterno che si applica al dial plan. Quando si crea il numero di accesso per la chiamata in ingresso, si selezionano le aree geografiche che associano il numero di accesso con i dial plan appropriati.
  
Si specifica anche l'ambito del dial plan: ambito utente, ambito del pool o ambito del sito. A ogni utente viene assegnato il dial plan dall'ambito più ristretto che si applica all'utente. Ad esempio, a un utente viene assegnato un dial plan a livello di utente, se si applica. Se non si applica un dial plan a livello di utente, all'utente viene assegnato un dial plan a livello di pool. Se non si applica un dial plan a livello di pool, all'utente viene assegnato un dial plan a livello di sito. Se non si applica un dial plan a livello di sito, all'utente viene assegnato il dial plan globale. 
  
Prima di configurare i dial plan, è importante pianificare il nome e l'uso delle aree geografiche. Le considerazioni seguenti si applicano alle aree dei servizi di conferenza telefonica con accesso esterno:
  
- In genere un'area geografica è associata a un ufficio o a un gruppo di uffici.
    
- Le lingue sono associate ai numeri di accesso per la chiamata in ingresso. Se si supportano aree geografiche con più lingue, è necessario decidere come definire le aree per il supporto di più lingue. Ad esempio, è possibile definire più aree in base a una combinazione di geografia e lingua oppure definire una singola area geografica in base alla geografia e avere un numero di accesso esterno diverso per ogni lingua.
    
- Quando un utente pianifica una riunione, per impostazione predefinita la riunione usa l'area specificata dal dial plan dell'utente.
    
- Per impostazione predefinita, tutti i numeri di accesso esterno per l'area sono inclusi nell'invito alla riunione.
    
- È importante assegnare un nome alle aree geografiche in modo che siano chiaramente riconoscibili. L'utente può usare i nomi delle aree geografiche per modificare l'area geografica di una riunione in modo da includere nell'invito diversi numeri di accesso. Quando gli utenti usano Outlook per pianificare una riunione, l'utente usa il componente aggiuntivo riunione online per Skype for business per cambiare l'area geografica.
    
- Le aree geografiche devono essere progettate in modo che tutti gli invitati che desiderano connettersi a una conferenza possano visualizzare un numero di accesso locale nell'invito alla conferenza.
    
- È possibile configurare l'ordine in cui i numeri di accesso all'interno di un'area vengono visualizzati nella pagina delle impostazioni di conferenza telefonica con accesso esterno (e, di conseguenza, nell'ordine in cui vengono visualizzati nell'invito alla conferenza) usando i cmdlet di Skype for Business Server Management Shell.
    
- Qualsiasi utente da qualsiasi luogo può chiamare un numero di accesso esterno per partecipare a una conferenza.
    
Per altre informazioni sulla creazione di un dial plan, vedere [creare o modificare un dial plan in Skype for Business Server](../../deploy/deploy-enterprise-voice/dial-plans.md) e [creare o modificare una regola di normalizzazione in Skype for business](../../deploy/deploy-enterprise-voice/normalization-rules.md). 
  
## <a name="plan-for-conference-directories"></a>Pianificare le directory conferenza

Le directory conferenza mantengono una mappatura tra l'ID riunione alfanumerico usato da un partecipante per partecipare a una conferenza quando si usa Skype for business e l'ID conferenza numerico che viene usato da un partecipante di conferenza telefonica con accesso esterno per partecipare alla conferenza. Il formato dell'ID conferenza è il seguente:
  
```
<housekeeping digit (1 digit)><conference directory (usually 1-2 digits)><conference number (variable number of digits><check digit (1 digit)>
```

La creazione di più directory conferenza garantirà che gli ID conferenza rimarranno invariati finché non verrà creata una quantità significativa di conferenze. In un'organizzazione con un numero tipico di conferenze per ogni utente, è consigliabile creare una directory conferenza per ogni utenti di 999 nel pool. Usando questa linea guida, gli ID conferenza possono in genere essere mantenuti piccoli. Tuttavia, una volta che il numero di directory conferenza (tra i pool) supera 9, il numero dell'ID conferenza crescerà per supportare altre conferenze.
  
## <a name="plan-for-a-conferencing-policy-that-allows-dial-in-access"></a>Pianificare un criterio di conferenza che consente l'accesso tramite chiamata in ingresso

Le conferenze devono essere abilitate per l'accesso esterno quando si configurano i criteri di conferenza. Per impostazione predefinita, le conferenze abilitate per l'accesso esterno includono le informazioni seguenti nell'invito alla conferenza:
  
- ID conferenza numerico che identifica la conferenza
    
- Uno o più numeri di accesso PSTN
    
- Un collegamento a una pagina delle impostazioni di conferenza telefonica con accesso esterno, che contiene un elenco completo dei numeri di Access con le lingue associate; una posizione per creare, reimpostare o sbloccare i numeri di identificazione personali (pin); e altre informazioni, ad esempio i controlli DTMF (Dual-Tone Multi-Frequency)
    
Per altre informazioni sui criteri di conferenza, vedere Configurare i servizi di [conferenza telefonica con accesso esterno in Skype for Business Server](../../deploy/deploy-conferencing/dial-in-conferencing.md) e [gestire i criteri di conferenza in Skype for Business Server](../../manage/conferencing/conferencing-policies.md).  

## <a name="support-for-enterprise-and-anonymous-users"></a>Supporto per utenti aziendali e anonimi

I servizi di conferenza telefonica con accesso esterno supportano utenti Enterprise e Anonymous. Gli utenti aziendali hanno le credenziali dei servizi di dominio Active Directory e gli account di Skype for Business Server all'interno dell'organizzazione. Gli utenti anonimi non hanno credenziali aziendali all'interno dell'organizzazione. Nel contesto dei servizi di conferenza telefonica con accesso esterno, un utente dell'organizzazione di un partner federato che usa la rete PSTN per connettersi a una conferenza viene considerato come un utente anonimo. Per i servizi di conferenza telefonica con accesso esterno, a differenza di altri contesti, gli utenti federati non vengono autenticati.
  
Gli utenti aziendali o i responsabili delle conferenze che partecipano a una conferenza abilitata per la chiamata in accesso esterno compongono uno dei numeri di accesso alla conferenza e quindi viene richiesto di immettere l'ID conferenza. Se una direttrice non è ancora entrata nella riunione, gli utenti possono immettere l'estensione UC (Unified Communications) o il numero di telefono completo e aggiungere o aspettare di essere ammessi da una direttrice. L'organizzatore della riunione può partecipare alla riunione come leader immettendo solo il PIN. Il server front-end usa la combinazione di numero di telefono completo o estensione e PIN per associare gli utenti aziendali in modo univoco alle credenziali di Active Directory. Di conseguenza, gli utenti dell'organizzazione vengono autenticati e identificati per nome nella conferenza. Gli utenti aziendali possono anche assumere un ruolo di conferenza predefinito dall'organizzatore.
  
> [!NOTE]
> Gli utenti aziendali che accedono da un telefono di Office IP o da Skype for Business Server Attendant non vengono richiesti per il proprio numero di telefono perché sono già autenticati. 
  
Utenti anonimi che desiderano partecipare a una conferenza telefonica con accesso esterno, digitare un numero di Access per le conferenze e quindi viene richiesto di immettere l'ID conferenza. Anche agli utenti anonimi non autenticati viene richiesto di registrare il proprio nome. Il nome registrato identifica gli utenti non autenticati nella conferenza. Gli utenti anonimi non sono ammessi alla conferenza fino a quando almeno un leader o un utente autenticato non partecipa e non è possibile assegnare loro un ruolo predefinito.
  
> [!NOTE]
> Gli utenti aziendali che scelgono di non immettere il proprio numero di telefono e il PIN non vengono autenticati. Viene richiesto di registrare il proprio nome e di essere trattati come utenti anonimi nella conferenza. 
  
Quando si pianifica una riunione, l'organizzatore della riunione può scegliere di limitare l'accesso alla riunione rendendo la riunione chiusa o bloccata. In questo caso, gli utenti con accesso esterno vengono richiesti per l'autenticazione. 
  
- Se gli utenti con accesso esterno non riescono o scelgono di non eseguire l'autenticazione, vengono trasferiti nella sala di attesa fino a quando un leader non li accetta o li rifiuta oppure viene disconnesso.
    
- Dopo l'ammissione a una conferenza, gli utenti con accesso esterno possono partecipare alla parte audio della conferenza e possono esercitare i comandi DTMF (Dual-Tone Multi-Frequency) usando la tastiera del telefono.
    
- I responsabili delle connessioni telefoniche con accesso esterno possono esercitare i comandi DTMF per attivare o disattivare l'attivazione o disattivazione dei partecipanti, bloccare o sbloccare la conferenza, ammettere gli utenti nella sala di attesa e attivare o disattivare gli annunci di entrata e uscita.
    
- I responsabili possono anche usare un comando DTMF per ammettere tutti gli utenti della sala di attesa, che modificano le autorizzazioni della riunione per consentire a tutti i partecipanti di accedervi. 
    
- Tutti i partecipanti alla chiamata in accesso esterno possono esercitare i comandi DTMF per ascoltare la guida, ascoltare il roster della conferenza e disattivare l'audio.
    
- I partecipanti alla chiamata in ingresso (ovvero, indipendentemente dal fatto che abbiano o meno la chiamata PSTN), ascoltano annunci personali durante la conferenza, ad esempio se sono stati disattivati o riattivati, se la riunione è stata registrata o se qualcuno sta aspettando nella sala di attesa.
    
    > [!NOTE]
    > Partecipanti che partecipano alla conferenza facendo clic su un collegamento invece di effettuare la chiamata in non si sentono annunci personali. 
  

