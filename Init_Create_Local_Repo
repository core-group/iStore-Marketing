#! /bin/sh
# install XCode Command Line Tools
/usr/bin/touch /tmp/.com.apple.dt.CommandLineTools.installondemand.in-progress;
PROD=$(softwareupdate -l |
  grep "\*.*Command Line" |
  head -n 1 | awk -F"*" '{print $2}' |
  sed -e 's/^ *//' |
  tr -d '\n')
softwareupdate -i "$PROD" -v;
# Clone the iStore-Marketing Repo into Library
git clone https://github.com/core-group/iStore-Marketing.git /Shared\ Items/Techs/iStore_Marketing
# Copy LaunchDaemon
cp /Shared\ Items/Techs/iStore_Marketing/com.core.istore.run_mrkting_gitpull.plist /Library/LaunchDaemons/
launchctl load -w /Library/LaunchDaemons/com.core.istore.run_mrkting_gitpull.plist
