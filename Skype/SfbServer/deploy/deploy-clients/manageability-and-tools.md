---
title: Skype Gestibilità e strumenti del sistema sala
ms.author: v-mahoffman
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leggere questo argomento per informazioni sugli strumenti di gestione per Skype Room System.
ms.openlocfilehash: 04b609e14b6ccffb5224a3041b1e8be25dcf7574
ms.sourcegitcommit: 65a10f80e5dfd67b2778e09f5f92c21ef09ce36a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/04/2021
ms.locfileid: "60758138"
---
# <a name="skype-room-system-manageability-and-tools"></a>Skype Gestibilità e strumenti del sistema sala
 
Leggere questo argomento per informazioni sugli strumenti di gestione per Skype Room System.
  
## <a name="administrative-portal"></a>Portale amministrativo

Per Skype for Business Server distribuzioni locali, è possibile utilizzare il portale amministrativo di Skype Room System per gestire e monitorare attivamente le distribuzioni di Skype Room System all'interno dell'organizzazione.
  
Per ulteriori informazioni, vedere l'articolo seguente:
  
- [Distribuire il portale Web amministrativo di SRS v1 in Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Exchange Elenco di controllo

- Verificare che l'individuazione automatica sia impostata e che sia disponibile un record A/CNAME DNS interno per autodiscover.domain.com.
    
- Ping autodiscover (ad esempio, Ping Autodiscover.contoso.com).
    
- Testare il servizio di individuazione automatica con Microsoft Connectivity Analyzer Tool. Scegliere il primo test, "Non è possibile accedere con Office Outlook".
    
- Se la sala riunioni dispone già di una cassetta postale per le risorse, estendere questo account per il Skype Room System (script di esempio nella parte inferiore della pagina).
    
## <a name="skype-for-business-checklist"></a>Skype for Business Elenco di controllo

- Eseguire gli strumenti seguenti:
    
  - Skype for Business Best Practices Analyzer     
  - Skype for Business Strumento di analisi dell'integrità (Excel)    
  - Skype for Business Analizzatore connettività a 32 bit o a 64 bit
    
- Esaminare [Utili nuovi strumenti di risoluzione dei](/archive/blogs/educloud/useful-new-troubleshooting-and-analysis-tools-for-office-365)problemi e analisi per Office 365 . Verificare di disporre di un pool Skype for Business e di un server web apps Office e di poter condividere una PowerPoint deck utilizzando il client Skype for Business.
    
- Se la sala riunioni dispone già di una cassetta postale per le risorse, abilitarla per Skype for Business.
    
- Se necessario, richiedere un DID (numero di telefono) per il sistema Sala riunioni e aggiornare il campo Telefono generale nello strumento Active Directory.
    
## <a name="network"></a>Rete

- Assicurarsi di disporre di una connessione di rete cablata per il Skype Room System.
    
- Leggere la Guida alla pianificazione della rete per Skype for Business.
    
- Richiedere una valutazione Skype for Business di rete da un partner Skype for Business partner.
    
- Leggere i dati sulle prestazioni acquisiti nello Skype for Business Health Analysis Tool (Excel).
    
- Eseguire lo strumento di analisi di rete.
    
- Eseguire lo strumento di diagnostica pre-chiamata.
    
## <a name="skype-room-system-security"></a>Skype Sicurezza del sistema sala

Skype Room System è un sistema incorporato che può essere completamente integrato in una distribuzione di Windows, utilizzando il modello di sicurezza Skype for Business, la gestione dei diritti e gli strumenti di gestione, ad esempio SCOM. Le funzionalità includono:
  
- Un filtro di scrittura per impedire la scrittura su disco in modalità utente 
    
- App Locker per impedire l'esecuzione di app non autorizzate. Tutte le porte USB sono disabilitate in modalità utente.
    
  - Nessuna app o visualizzatore standard risiede nell'hardware Skype Room System. Il rendering di tutto il contenuto viene eseguito tramite protocolli HTTP o RDP.
    
  - Il PC dell'appliance esegue Windows sistema operativo Embedded Standard 7. Tutti i componenti hardware, inclusi i dispositivi, sono forniti dai partner OEM.
    
  - Aggiunta facoltativa al dominio a Servizi di dominio Active Directory, abilitando la gestione e il controllo degli account di sicurezza locali.
    
- Puoi anche gestire l'account amministratore locale usando l'Skype for Business di amministrazione locale.
    
- Skype Room System viene aggiornato tramite i processi standard di Microsoft Update.
    
- Skype Room System si connette con Skype for Business.
    
  - Skype for Business utilizza la crittografia end-to-end e l'autorizzazione per tutte le modalità di comunicazione
    
  - Skype Room System supporta gli standard Skype for Business sicurezza e conformità. Per ulteriori informazioni, vedere [Plan for security in Skype For Business Server.](../../plan-your-deployment/security/security.md)
    
## <a name="license"></a>License

Verificare di usare un Servizio di gestione delle chiavi per l'attivazione del software. In tal caso, potrebbe essere necessario controllare o aggiungere la chiave Skype for Business client Servizio di gestione delle chiavi chiave. Se non si utilizza Servizio di gestione delle chiavi, richiedere il codice "Product Key" per contratti multilicenza per il codice ad attivazione Skype for Business client.
  
## <a name="license-keys"></a>Codici di licenza

Skype Room System esegue il Skype for Business desktop in background. Se Skype Room System è un membro di dominio, scoprirà la tua Servizio di gestione delle chiavi. (e se ha il codice Servizio di gestione delle chiavi per contratti multilicenza, verrà attivato automaticamente). I contratti multilicenza forniscono anche un codice ADK, che viene immesso quando viene visualizzato xxxxx-xxxxx-xxxxx-xxxxx. È necessario l'accesso a Internet per l'attivazione tramite codice ad attivazione Servizio di gestione delle chiavi). Per ulteriori informazioni, vedere Volume activation of Office 2013.
  
- Per immettere il codice ADK, passare a OEM Impostazioni \> SRS Licensing Tool. Fare clic su Controlla stato. Quando lo stato indica "il prodotto non è attivato", immetti il codice.
    
- Se durante l'attivazione viene visualizzato un errore che indica "Il servizio gestione licenze software ha segnalato che il codice Product Key non è valido", verificare che:
    
  - Il tasto è stato immesso correttamente.
    
  - È stato immesso Skype for Business codice ADK e non un'altra chiave.
    
  - Il sistema ha accesso a Internet.
    
- È possibile eseguire l'attivazione tramite telefono, ma è necessario aver prima tentato di eseguire l'attivazione utilizzando lo strumento di gestione delle licenze SRS. Per eseguire l'attivazione tramite telefono, avviare una riunione di prova (non una chiamata di prova perché è troppo breve). Nell'Office guidata selezionare Attivazione telefonica, chiamare Microsoft, digitare il numero lungo e immettere una risposta.
    
## <a name="certificate-authority"></a>Autorità di certificazione

Verificare che l'autorità di certificazione utilizzata per emettere il certificato Office Web Apps Server 2013 abbia un percorso HTTP incluso nella proprietà Certificate Revocation List.
  
Importare il file del certificato (con estensione crt) nel Skype Room System se si utilizza Skype for Business Server. È facilmente ottenuta dalla condivisione CertEnroll del server CA o nella cartella Radice attendibile di qualsiasi DOMINIO aggiunto al PC.
  
## <a name="certificates"></a>Certificati

Verificare che l'Autorità di certificazione abbia un percorso http per l'elenco di revoche di certificati. In caso contrario, aggiornare l'autorità di certificazione per includerne una.
  
Installare i certificati nella configurazione dell'amministratore di Skype Room System in System Impostazioni Certificate Manager.Install certificates in the admin setup of the Skype Room System under System Impostazioni \> Certificate Manager. È necessaria l'Enterprise ca radice per il certificato interno.
  
Un modo per ottenere i certificati necessari è individuare l'autorità di certificazione che ha emesso i certificati. Ad Skype for Business Server, in un PC in Skype for Business fare clic su Impostazioni \> Strumenti Conferenza telefonica con accesso \> Impostazioni. Verrà aperta una pagina Web protetta dall'autorità di certificazione che ha emesso i certificati interni. Fare clic sull'icona Blocca sulla barra degli indirizzi del browser per visualizzare un report sulla sicurezza. Fare clic su Visualizza certificati ed esaminare la proprietà Punto di distribuzione CRL. Il secondo parametro CN deve essere il nome del server dell'autorità di certificazione. Apri ora Windows Explorer per \\ \< CA Server Name \> l'indirizzo \CertEnroll. Copiare i due file crl e il file crt in un'unità flash e metterlo nella parte sinistra della scheda SMART.
  
Importare il file crt nella Skype Room System nella cartella Autorità di certificazione sala attendibile.
  
Importare i file crl nel Skype Room System nella cartella Autorità di certificazione intermedie. È necessario modificare il filtro delle estensioni di file in Gestione certificati in .crl per visualizzare i file.
  
Nota: il server Office Web Apps 2013 può condividere la stessa CA Skype for Business. In caso di non accesso, non sarà possibile condividere PowerPoint in una riunione. Verificare con l'IT e ottenere i file CRT e CRL dalla condivisione di rete CA CertEnroll, come spiegato in precedenza. 
  
L'appartenenza al dominio può semplificare alcuni aspetti, perché è possibile considerare il Skype Room System come un sistema Windows e può fare affidamento su Active Directory per alcuni degli aspetti del certificato. Tuttavia, è meglio gestirlo manualmente.
