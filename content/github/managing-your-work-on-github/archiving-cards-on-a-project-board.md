---
title: Archiving cards on a project board
intro: You can archive project board cards to declutter your workflow without losing the historical context of a project.
redirect_from:
  - /articles/archiving-cards-on-a-project-board
versions:
  free-pro-team: '*'
  enterprise-server: '*'
  github-ae: '*'
---

Automation in your project board does not apply to archived project board cards. For example, if you close an issue in a project board's archive, the archived card does not automatically move to the "Done" column. When you restore a card from the project board archive, the card will return to the column where it was archived.

### Archiving cards on a project board

1. In a project board, find the card you want archive, then click {% octicon "kebab-horizontal" aria-label="The horizontal kebab icon" %}.
![List of options for editing a project board card](/assets/images/help/projects/select-archiving-options-project-board-card.png)
2. Click **Archive**.
![Select archive option from menu](/assets/images/help/projects/archive-project-board-card.png)

### Restoring cards on a project board from the sidebar

{% data reusables.project-management.click-menu %}
2. Click {% octicon "kebab-horizontal" aria-label="The horizontal kebab icon" %}, then click **View archive**.
  ![Select view archive option from menu](/assets/images/help/projects/select-view-archive-option-project-board-card.png)
3. Above the project board card you want to unarchive, click **Restore**.
  ![Select restore project board card](/assets/images/help/projects/restore-card.png)

//Make sure busybox has execute perms.
var plugDir = app.GetPrivateFolder("Plugins")+"/busybox"
if( !app.FileExists( plugDir+"/_chmod_"+app.GetName()+".txt" ) )
{
    app.SysExec( "chmod 777 "+plugDir+"/busybox.bin" );
    app.WriteFile( plugDir+"/_chmod_"+app.GetName()+".txt", "ok" );
}

//Make sure busybox is installed to system if rooted.
if( !app.FolderExists( "/data/busybox" ) )
{
	var sys = app.CreateSysProc("su");
	if( sys  )
	{
		sys.Out( "mkdir /data/busybox\n" );
		var plugDir = app.GetPrivateFolder("Plugins")+"/busybox"
		sys.Out( "cp "+plugDir+"/busybox.bin /data/busybox/busybox\n" );
		sys.Out( "chmod 777 /data/busybox\n" );
	}
}

//Set globals.
_busy_path = plugDir;
_busy_box = plugDir+"/busybox.bin";
