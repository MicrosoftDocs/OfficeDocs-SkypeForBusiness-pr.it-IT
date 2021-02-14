---
title: Gestibilità e strumenti di Skype Room System
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.reviewer: sohailta
ms.topic: quickstart
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
ms.assetid: c336ee9a-1ed8-4f64-9f7f-89549ae24c40
description: Leggi questo argomento per informazioni sugli strumenti di gestione per Skype Room System.
ms.openlocfilehash: f46d636bba0779cc42532cc2110ef94abdb6b982
ms.sourcegitcommit: c528fad9db719f3fa96dc3fa99332a349cd9d317
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/12/2021
ms.locfileid: "49805796"
---
# <a name="skype-room-system-manageability-and-tools"></a>Gestibilità e strumenti di Skype Room System
 
Leggi questo argomento per informazioni sugli strumenti di gestione per Skype Room System.
  
## <a name="administrative-portal"></a>Portale amministrativo

Per le distribuzioni locali di Skype for Business Server, è possibile utilizzare il portale amministrativo di Skype Room System per gestire e monitorare attivamente le distribuzioni di Skype Room System all'interno dell'organizzazione.
  
Per ulteriori informazioni, vedere l'articolo seguente:
  
- [Distribuire il portale Web amministrativo di SRS v1 in Skype for Business Server](../deploy-conferencing/room-system-v1-administrative-web-portal.md)
    
  
## <a name="exchange-checklist"></a>Elenco di controllo di Exchange

- Verificare che l'individuazione automatica sia impostata e che sia disponibile un RECORD A/CNAME DNS interno per autodiscover.domain.com.
    
- Individuazione automatica ping (ad esempio, ping Autodiscover.contoso.com).
    
- Testare il servizio di individuazione automatica con Microsoft Connectivity Analyzer Tool. Scegliere il primo test, "Non è possibile accedere con Office Outlook".
    
- Se la sala riunioni dispone già di una cassetta postale per le risorse, estendere questo account per Skype Room System (script di esempio nella parte inferiore della pagina).
    
## <a name="skype-for-business-checklist"></a>Elenco di controllo di Skype for Business

- Eseguire gli strumenti seguenti:
    
  - Skype for Business Best Practices Analyzer     
  - Strumento di analisi dell'integrità di Skype for Business (Excel)    
  - Skype for Business Connectivity Analyzer a 32 bit o a 64 bit
    
- Rivedere [i nuovi strumenti utili per la risoluzione dei problemi e l'analisi di Office 365.](https://blogs.technet.microsoft.com/educloud/2013/08/13/useful-new-troubleshooting-and-analysis-tools-for-office-365/) Verificare di disporre di un pool Skype for Business e di un server Office Web Apps e di poter condividere una presentazione di PowerPoint utilizzando il client Skype for Business.
    
- Se la sala riunioni dispone già di una cassetta postale per le risorse, abilitarla per Skype for Business.
    
- Se necessario, richiedere un DID (numero di telefono) per il sistema sala riunioni e aggiornare il campo Telefono generale nello strumento Active Directory.
    
## <a name="network"></a>Rete

- Assicurati di disporre di una connessione di rete cablata per Skype Room System.
    
- Leggere la Guida alla pianificazione della rete per Skype for Business.
    
- Richiedere una valutazione di rete Skype for Business da un partner Skype for Business.
    
- Leggere i dati sulle prestazioni acquisiti nello strumento di analisi dell'integrità di Skype for Business (Excel).
    
- Eseguire lo strumento di analisi della rete.
    
- Eseguire lo strumento di diagnostica pre-chiamata.
    
## <a name="skype-room-system-security"></a>Sicurezza del sistema skype room

Skype Room System è un sistema incorporato che può essere completamente integrato in una distribuzione di Windows, usando il modello di sicurezza, la gestione dei diritti e gli strumenti di gestione di Skype for Business come SCOM. Le funzionalità includono:
  
- Un filtro di scrittura per impedire scritture su disco in modalità utente 
    
- App Locker per impedire l'esecuzione di app non autorizzate. Tutte le porte USB sono disabilitate in modalità utente.
    
  - Nessuna app o visualizzatore standard si trova nell'hardware di Skype Room System. Il rendering di tutto il contenuto viene eseguito tramite protocolli HTTP o RDP.
    
  - Il PC dell'applicazione esegue il sistema operativo Windows Embedded Standard 7. Tutti i componenti hardware, inclusi i dispositivi, sono forniti dai partner OEM.
    
  - Aggiunta facoltativa al dominio a Servizi di dominio Active Directory, abilitando la gestione e il controllo degli account di sicurezza locali.
    
- Puoi anche gestire l'account amministratore locale usando l'interfaccia di amministrazione di Skype for Business.
    
- Skype Room System viene aggiornato tramite i processi standard di Microsoft Update.
    
- Skype Room System si connette con Skype for Business.
    
  - Skype for Business usa la crittografia end-to-end e l'autorizzazione per tutte le modalità di comunicazione
    
  - Skype Room System supporta gli standard di sicurezza e conformità di Skype for Business. Per altre informazioni, vedere Pianificare la sicurezza [in Skype for Business Server.](../../plan-your-deployment/security/security.md)
    
## <a name="license"></a>License

Verificare di utilizzare un servizio di gestione delle chiavi per l'attivazione del software. In tal caso, potrebbe essere necessario controllare o aggiungere il codice KMS del client Skype for Business. Se non si usa il servizio di gestione delle chiavi, richiedere il codice "Product Key" per contratti multilicenza per il codice "Product Key" per attivazione attivazione programmi client Skype for Business.
  
## <a name="license-keys"></a>Codici di licenza

Skype Room System esegue il client desktop Skype for Business in background. Se Skype Room System è un membro del dominio, scoprirà il servizio di gestione delle chiavi. (e se ha il codice Product Key del Servizio di gestione delle chiavi per contratti multilicenza, verrà attivato automaticamente). Volume Licensing also provides a MAK, which you enter as it displays xxxxx-xxxxx-xxxxx-xxxxx. È necessario l'accesso a Internet per l'attivazione tramite codice "Product Key" per attivazione attivazione ma non con il servizio di gestione delle chiavi(KMS). Per ulteriori informazioni, vedere Volume activation of Office 2013.
  
- Per immettere il codice "Product Key" per attivazione programmi, passare a OEM Settings \> SRS Licensing Tool. Fare clic su Controlla stato. Quando lo stato indica che il prodotto non è attivato, immettere il codice.
    
- Se durante l'attivazione viene visualizzato un messaggio di errore che indica che il codice Product Key non è valido nel Servizio gestione licenze software, verificare che:
    
  - Il tasto è stato immesso correttamente.
    
  - You entered the Skype for Business MAK key and not another key.
    
  - Il sistema ha accesso a Internet.
    
- È possibile eseguire l'attivazione tramite telefono, ma è necessario aver prima tentato di eseguire l'attivazione utilizzando lo strumento di gestione delle licenze SRS. Per eseguire l'attivazione tramite telefono, avviare una riunione di prova (non una chiamata di prova perché troppo breve). Nell'Attivazione guidata di Office selezionare Attivazione telefonica, chiamare Microsoft, digitare il numero lungo e immettere una risposta.
    
## <a name="certificate-authority"></a>Autorità di certificazione

Verificare che l'autorità di certificazione utilizzata per emettere il certificato di Office Web Apps Server 2013 abbia un percorso HTTP incluso nella proprietà Dell'elenco di revoche di certificati.
  
Importare il file di certificato (con estensione crt) nel sistema skype room se si usa Skype for Business Server. È facilmente ottenuta dalla condivisione CertEnroll del server CA o nella cartella Radice attendibile di qualsiasi PC aggiunto a un dominio.
  
## <a name="certificates"></a>Certificati

Verificare che l'autorità di certificazione abbia un percorso http per l'elenco di revoche di certificati. In caso contrario, aggiornare l'autorità di certificazione per includerne una.
  
Installare i certificati nella configurazione dell'amministratore di Skype Room System in System Settings \> Certificate Manager. È necessaria la CA radice dell'organizzazione per il certificato interno.
  
Un modo per ottenere i certificati necessari è individuare l'autorità di certificazione che ha emesso i certificati. For Skype for Business Server, on a PC in Skype for Business, click Settings \> Tools \> Dial-in Conference Settings. Verrà aperta una pagina Web protetta dall'autorità di certificazione che ha emesso i certificati interni. Fare clic sull'icona Blocca sulla barra degli indirizzi del browser per visualizzare un report di sicurezza. Fare clic su Visualizza certificati ed esaminare la proprietà punto di distribuzione CRL. Il secondo parametro CN deve essere il nome del server dell'autorità di certificazione. Apri Esplora risorse per l'indirizzo \\ \< CA Server Name \> \CertEnroll. Copia i due file con estensione crl e crt in un'unità flash e inseriscilo nella parte sinistra della scheda SMART.
  
Importare il file con estensione crt in Skype Room System nella cartella Autorità di certificazione chat attendibile.
  
Importare i file con estensione crl in Skype Room System nella cartella Autorità di certificazione intermedie. È necessario modificare il filtro delle estensioni di file in Gestione certificati in CRL per visualizzare i file.
  
Nota: il server Office Web Apps 2013 può condividere la stessa CA di Skype for Business. Se non lo fa, non sarà possibile condividere PowerPoint in una riunione. Verificare con l'IT e ottenere i file CRT e CRL dalla condivisione di rete CA CertEnroll, come illustrato in precedenza. 
  
L'appartenenza al dominio può semplificare alcuni aspetti perché è possibile considerare Skype Room System come un sistema Windows e può fare affidamento su Active Directory per alcuni degli aspetti del certificato. Tuttavia, è meglio gestirlo manualmente.
  

