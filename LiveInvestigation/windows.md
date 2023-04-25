### ファイルの操作監視
```
$watcher = New-Object System.IO.FileSystemWatcher
$watcher.Path = "C:\Windows\System32\drivers"  # 監視するディレクトリ
$watcher.Filter = "*"  # ファイル名
$watcher.IncludeSubdirectories = $true
$watcher.EnableRaisingEvents   = $true

# イベントリスナー
$action = {
    $path = $Event.SourceEventArgs.FullPath
    $changeType = $Event.SourceEventArgs.ChangeType
    Write-Host "$(Get-Date), $changeType, $path"
}

# イベントの登録
Register-ObjectEvent $watcher "Created" -Action $action
Register-ObjectEvent $watcher "Changed" -Action $action
Register-ObjectEvent $watcher "Deleted" -Action $action
Register-ObjectEvent $watcher "Renamed" -Action $action

while ($true) { sleep 1 }
```
