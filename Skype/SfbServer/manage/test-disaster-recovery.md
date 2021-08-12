---
title: Test di ripristino di emergenza in Skype for Business Server
ms.reviewer: ''
ms.author: v-cichur
author: cichur
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: skype-for-business-itpro
f1.keywords:
- NOCSH
localization_priority: Normal
description: Eseguire un ripristino di sistema per un server Skype for Business Server pool per testare il processo di ripristino di emergenza documentato
ms.openlocfilehash: 147f947ca0f43f3ca3f05557e992026efb4d524c81073e2d5db3be42f51aa47d
ms.sourcegitcommit: a17ad3332ca5d2997f85db7835500d8190c34b2f
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/05/2021
ms.locfileid: "54324205"
---
# <a name="disaster-recovery-testing-in-skype-for-business-server"></a>Test di ripristino di emergenza in Skype for Business Server

Eseguire un ripristino di sistema per un server Skype for Business Server pool per testare il processo di ripristino di emergenza documentato. Questo test simula un errore hardware completo per un server e garantisce che le risorse, i piani e i dati siano disponibili per il ripristino. Provare a ruotare lo stato attivo del test ogni mese in modo che l'organizzazione testa ogni volta l'errore di un server o di un'altra attrezzatura. 

Si noti che la pianificazione in base alla quale le organizzazioni eseguono i test di ripristino di emergenza varia. È molto importante che i test di ripristino di emergenza non vengono ignorati o ignorati. 

Esportare la Skype for Business Server, i criteri e le impostazioni di configurazione in un file. Tra l'altro, questo file può essere utilizzato per ripristinare queste informazioni nell'archivio di gestione centrale dopo un aggiornamento, un errore hardware o un altro problema che ha comportato la perdita di dati.

Importare Skype for Business Server topologia, criteri e impostazioni di configurazione nell'archivio di gestione centrale o nel computer locale, come illustrato nei comandi seguenti: 

`Import-CsConfiguration -ByteInput <Byte[]> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]`

`Import-CsConfiguration -FileName <String> [-Force <SwitchParameter>] [-LocalStore <SwitchParameter>]` 

Per eseguire il backup dei dati di produzione:

- Eseguire il backup dei database RTC e LCSLog utilizzando il processo di backup SQL Server standard per eseguire il dump del database in un dispositivo di dump su file o su nastro.
- Utilizzare un'applicazione di backup di terze parti per eseguire il backup dei dati su file o su nastro.
- Utilizzare il cmdlet Export-CsUserData per creare un'esportazione XML dell'intero database RTC.
- Utilizzare il backup del file system o il backup di terze parti per eseguire il backup del contenuto delle riunioni e dei log di conformità.
- Utilizzare lo Export-CsConfiguration da riga di comando per eseguire il backup Skype for Business Server impostazioni.

Il primo passaggio della procedura di failover include uno spostamento forzato degli utenti dal pool di produzione al pool di ripristino di emergenza. Si tratta di uno spostamento forzato perché il pool di produzione non sarà disponibile per accettare la rilocazione dell'utente.

Il Skype for Business Server utente di spostamento è in effetti una modifica a un attributo nell'oggetto account utente oltre a un aggiornamento dei record nel database RTC SQL. Questi dati possono essere ripristinati dal dispositivo di dump di backup originale dal SQL Server di produzione utilizzando il processo di ripristino SQL Server standard o utilizzando un'utilità di backup/ripristino di terze parti.

Dopo il ripristino di questi dati, gli utenti possono connettersi in modo efficace al pool di ripristino di emergenza e funzionare come al solito. Per consentire agli utenti di connettersi al pool di ripristino di emergenza, sarà necessaria una modifica del record DNS.

Il pool Skype for Business di produzione farà riferimento ai client che utilizzano la configurazione automatica e i record DNS SRV di:

- SRV: _sip._tls.\<domain> /CNAME: SIP.\<domain>
- CNAME: SIP.\<domain> /cvc-pool-1.\<domain>

Per facilitare il failover, questo record CNAME deve essere aggiornato in modo da fare riferimento all'FQDN DROCSPool:

- CNAME: SIP.<domain> /DROCSPool.\<domain>
- Sip.\<domain>
- AV.\<domain>
- webconf.\<domain>
