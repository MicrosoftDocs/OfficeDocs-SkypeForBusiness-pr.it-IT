---
title: Gestibilità e strumenti per Skype room System
ms.author: v-lanac
author: lanachin
manager: serdars
audience: ITPro
ms.reviewer: davgroom
ms.topic: get-started-article
ms.prod: skype-for-business-itpro
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leggere questo argomento per informazioni sugli strumenti di gestione per Skype room System.
ms.openlocfilehash: 4ae57457eb244e7cf72183bfadba0bd0b89d44a6
ms.sourcegitcommit: ab47ff88f51a96aaf8bc99a6303e114d41ca5c2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2019
ms.locfileid: "36194442"
---
# <a name="skype-room-system-manageability-and-tools"></a>Gestibilità e strumenti per Skype room System
 
Leggere questo argomento per informazioni sugli strumenti di gestione per Skype room System.
  
## <a name="administrative-portal"></a>Portale amministrativo

Per le distribuzioni locali di Skype for Business Server, è possibile usare il portale di amministrazione di Skype room System per gestire e monitorare attivamente le distribuzioni di sistema room Skype all'interno dell'organizzazione.
  
Per altre informazioni, vedere l'articolo seguente:
  
- [Distribuire il portale Web amministrativo di SRS V1 in Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
## <a name="system-center-operations-manager"></a>System Center Operations Manager

Skype room System può essere monitorato tramite System Center Operations Manager (SCOM) scaricando il [Management Pack di Skype room System](https://www.microsoft.com/download/details.aspx?id=42320) e installarlo nel server di SCOM. Puoi usare SCOM per impostare gli avvisi, monitorare l'integrità del sistema room Skype, generare report uptime e molto altro. Skype room System include un agente di monitoraggio preinstallato che può essere configurato in maniera che punti al server SCOM. Vedere la Guida all'installazione fornita dal produttore del sistema Skype room System per sapere come configurare l'agente di monitoraggio in Skype room System.
  
## <a name="exchange-checklist"></a>Elenco di controllo di Exchange

- Verificare che l'individuazione automatica sia configurata e che sia disponibile un RECORD DNS interno A/CNAME per autodiscover.domain.com.
    
- Individuazione automatica ping (ad esempio, ping Autodiscover.contoso.com).
    
- Testare il servizio di individuazione automatica con lo strumento Microsoft Connectivity Analyzer. Scegliere il primo test, "non è possibile accedere con Office Outlook".
    
- Se nella sala riunioni è già presente una cassetta postale per le risorse, estendere l'account per il sistema di sala Skype (script di esempio nella parte inferiore della pagina).
    
## <a name="skype-for-business-checklist"></a>Elenco di controllo di Skype for business

- Eseguire gli strumenti seguenti:
    
  - Analizzatore delle procedure consigliate di Skype for business     
  - Strumento analisi integrità di Skype for business (Excel)    
  - Analizzatore connettività di Skype for Business 32 bit o 64 bit
    
- Rivedere [utili nuovi strumenti di risoluzione dei problemi e analisi per Office 365](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/). Verificare di avere un pool di Skype for business e un server di Office Web Apps e di condividere una presentazione di PowerPoint usando il client Skype for business.
    
- Se la sala riunioni ha già una cassetta postale delle risorse, Abilitala per Skype for business.
    
- Se necessario, Richiedi un DID (numero di telefono) per il sistema della sala riunioni e aggiorna il campo telefono generale nello strumento Active Directory.
    
## <a name="network"></a>Rete

- Verificare di avere una connessione di rete cablata per il sistema room Skype.
    
- Leggere la guida alla pianificazione della rete per Skype for business.
    
- Richiedi una valutazione della rete Skype for business da un partner di Skype for business.
    
- Leggere i dati sulle prestazioni acquisiti nello strumento analisi integrità di Skype for business (Excel).
    
- Eseguire lo strumento di analisi della rete.
    
- Eseguire lo strumento di diagnostica chiamata preliminare.
    
## <a name="skype-room-system-security"></a>Skype room System Security

Skype room System è un sistema embedded che può essere completamente integrato in una distribuzione Windows, usando il modello di sicurezza Skype for business, Rights Management e strumenti di gestione come SCOM. Le caratteristiche includono:
  
- Filtro di scrittura per impedire la scrittura del disco in modalità utente 
    
- App Locker per impedire l'utilizzo di app non autorizzate. Tutte le porte USB sono disabilitate in modalità utente.
    
  - Nessuna app o visualizzatore standard risiede nell'hardware del sistema Skype room. Viene eseguito il rendering di tutti i contenuti tramite protocolli HTTP o RDP.
    
  - Il PC Appliance esegue il sistema operativo Windows Embedded Standard 7. Tutti i componenti hardware, inclusi i dispositivi, sono forniti da partner OEM.
    
  - Il dominio facoltativo si unisce a servizi di dominio Active Directory (AD DS), consentendo la gestione e il controllo di account di sicurezza locali.
    
- Puoi anche gestire l'account di amministrazione locale usando l'interfaccia di amministrazione di Skype for business.
    
- Skype room System viene aggiornato tramite processi standard di Microsoft Update.
    
- Skype room System si connette a Skype for business.
    
  - Skype for business usa la crittografia end-to-end e l'autorizzazione per tutte le modalità di comunicazione
    
  - Skype room System supporta gli standard di sicurezza e conformità di Skype for business. Per altre informazioni, vedere [pianificare la sicurezza in Skype for Business Server](../../plan-your-deployment/security/security.md) .
    
## <a name="license"></a>Licenza

Verificare di usare un KMS per l'attivazione del software. In questo caso, potrebbe essere necessario controllare o aggiungere la chiave KMS del client Skype for business. Se non si usa KMS, richiedere il codice di licenza volume per Skype for Business client MAK.
  
## <a name="license-keys"></a>Codici di licenza

Skype room System esegue il client desktop Skype for business in background. Se Skype room System è un membro del dominio, verrà individuato il tuo KMS. (e se ha la chiave di KMS per contratti multilicenza che verrà attivata automaticamente). Contratti multilicenza offre anche un MAK, che viene immesso mentre viene visualizzato xxxxx-xxxxx-xxxxx-xxxxx. (È necessario l'accesso a Internet per l'attivazione usando MAK ma non KMS). Per altre informazioni, vedere attivazione del volume di Office 2013.
  
- Per immettere il codice Product Key, passare allo strumento \> di gestione licenze SRS delle impostazioni OEM. Fare clic su Controlla stato. Quando lo stato indica che "prodotto non è attivato", immettere la chiave.
    
- Se durante l'attivazione viene visualizzato un messaggio di errore che indica che "' il servizio di gestione licenze software ha riferito che il codice Product Key non è valido", quindi verificare che:
    
  - Il tasto è stato immesso correttamente.
    
  - È stato immesso il codice MAK Skype for business e non un altro tasto.
    
  - Il sistema ha accesso a Internet.
    
- È possibile eseguire l'attivazione tramite telefono, ma deve essere tentato di attivare prima di tutto l'uso dello strumento di gestione licenze SRS. Per eseguire l'attivazione tramite telefono, avviare una riunione di prova (non una chiamata di prova perché è troppo breve). Nell'attivazione guidata di Office selezionare Attivazione telefono, chiama Microsoft, digitare il numero lungo e immettere una risposta.
    
## <a name="certificate-authority"></a>Autorità di certificazione

Verificare che l'autorità di certificazione usata per emettere il certificato di Office Web Apps Server 2013 disponga di un percorso HTTP incluso nella proprietà elenco di revoche di certificati.
  
Se si usa Skype for Business Server, importare il file di certificato (con estensione CRT) nel sistema room Skype. Si ottiene facilmente dalla condivisione CertEnroll del server CA o nella cartella radice attendibile di qualsiasi PC collegato a un dominio.
  
## <a name="certificates"></a>Certificati

Verificare che l'autorità di certificazione disponga di un percorso http per l'elenco di revoche di certificati. In caso contrario, aggiornare la CA per includerne una.
  
Installare i certificati nella configurazione dell'amministratore del sistema di chat room in gestione \> certificati delle impostazioni di sistema. È necessaria la CA radice aziendale per il certificato interno.
  
Un modo per ottenere i certificati necessari consiste nell'individuare la CA che ha emesso i certificati. Per Skype for Business Server, su un PC in Skype for business, fare clic \> su \> Impostazioni conferenza telefonica con accesso esterno. Verrà aperta una pagina Web protetta dalla CA che ha emesso i certificati interni. Fare clic sull'icona di blocco nella barra degli indirizzi del browser per visualizzare un report di sicurezza. Fare clic su Visualizza certificati ed esaminare la proprietà punto di distribuzione CRL. Il secondo parametro CN deve essere il nome del server della CA. Aprire Esplora risorse per il nome \\ \< \>del server CA dell'indirizzo \CertEnroll. Copiare i due file CRL e il file CRT in un'unità flash e posizionarlo sul lato sinistro della SMART Board.
  
Importare il file con estensione CRT nel sistema della sala Skype in una cartella attendibile dell'autorità di certificazione della sala.
  
Importare i file CRL nel sistema room Skype nella cartella autorità di certificazione intermedie. È necessario modificare il filtro dell'estensione di file in Gestione certificati in CRL per visualizzare i file.
  
Nota: il server Office Web Apps 2013 può condividere la stessa CA di Skype for business. In caso contrario, non sarà possibile condividere PowerPoint in una riunione. Verificare con esso e ottenere i file CRT e CRL al di fuori della condivisione di rete della CA CertEnroll, come spiegato sopra. 
  
L'appartenenza a un dominio può semplificare alcuni aspetti perché è possibile trattare il sistema Skype room come sistema Windows e può contare su Active Directory per alcune delle funzioni del certificato. Tuttavia, è consigliabile gestirlo manualmente.
  

