# Slackula
Based on `udaykd09/dracula-slack`

### MacOS:
- Quit slack
- Open this file:
  ```
  /Applications/Slack.app/Contents/Resources/app.asar.unpacked/src/static/ssb-interop.js /Applications/Slack.app/Contents/Resources/app.asar.unpacked/src/static/ssb-interop_backup.js
  ```
- Paste this at the bottom:  
  ```
    document.addEventListener('DOMContentLoaded', function() {
        let tt__customCss = `
            body, .channel_header, #footer, .channel_title_info, #channel_topic_text { background: rgb(0, 43, 54); }
            .c-message__body { color: rgb(153, 174, 177); }
            #team_menu, .p-channel_sidebar { background: #000000 !important; }
            .c-presence--active {color: rgb(177, 202, 17) !important;}
            nav.p-channel_sidebar .p-channel_sidebar__channel--selected, .p-channel_sidebar__link--selected, .c-message_list__day_divider__label__pill, .p-message_pane .c-message_list.c-virtual_list--scrollbar > .c-scrollbar__hider:before { color: #eee !important; background: rgb(27, 139, 210) !important; }
            .c-message_list__day_divider__line { border-top-color: rgb(27, 139, 210) !important}
            #msg_input, #primary_file_button { background: #000000) !important; }
            #msg_form #msg_input { border-color: transparent; }
        `;
        $.ajax({
            url: 'https://raw.githubusercontent.com/snaptopixel/dracula-slack/master/slack.css',
            success: function(css) {
                $('<style></style>').appendTo('head').html(css + tt__customCss);
            }
        });
    });
  ```

Restart slack

Enjoy!
