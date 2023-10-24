# Pop-dark theme 43+

[<img src="Images/screenshot-dark.png">](Images/vm_exemple.png)

[[_TOC_]]

## Why is it?

This is a "port" of the Pop-os dark gnome-shell theme for gnome 43+.

I've been trying to keep the Pop-Os spirit and color scheme.

This is my first experience with CSS, and this theme was created for my personal use.

Do not except a bug free experience, this is WIP.

## What's new?

- Redisigned quick settings.
- Redisigned OSD
- Also themed some dialogs.

## How to install

Clone this repository and place the "Pop-dark-43" folder in your .themes directory.

## How to replicate Pop theme experience on any system

In addition to this shell theme, there are several things that can help you get almost the same experience as the official theme.

### Libadwaita theme

Install gnome-tweaks gradience and adw-gtk3 theme.

In gradience, allow for flatpak theming and use the Pop-dark preset.

With this all your GTK4 apps should look like Pop theme.

In gnome-tweaks, select adw-gtk3 theme for legacy applications. This way non GTK apps will use it and have the same window decorations as your GTK4 apps.

### Fix GTK3 window decorations

Open gradience and select the Pop-dark preset.

Go to the advanced tab and paste the following GTK3 CSS.

<p>
<details>
<summary>Expand/hide</summary>

<pre><code>
/*****************
 *WINDOW CONTROLS*
 *****************/

button.titlebutton.close,
windowcontrols > button.close {
  background-color: #f28c2a;
}

button.titlebutton.close:hover,
windowcontrols > button.close:hover {
  background-color: #5e5e5e;
}

button.titlebutton.close:active,
windowcontrols > button.close:active {
  background-color: #4e4e4e;
}

button.titlebutton { /* GTK3 */
  min-width: 20px;
  min-height: 20px;
}

button.titlebutton.minimize,
windowcontrols > button.minimize {
  background-color: transparent;
}

button.titlebutton.minimize:hover,
windowcontrols > button.minimize:hover {
  background-color: #5e5e5e;
}

button.titlebutton.minimize:active,
windowcontrols > button.minimize:active {
  background-color: #4e4e4e;
}

button.titlebutton.maximize,
windowcontrols > button.maximize {
  background-color: transparent;
}

button.titlebutton.maximize:hover,
windowcontrols > button.maximize:hover {
  background-color: #5e5e5e;
}

button.titlebutton.maximize:active,
windowcontrols > button.maximize:active {
  background-color: #4e4e4e;
}

button.titlebutton:backdrop {
  background-color: transparent;
}

/*****************
 *CONTROL WIDGETS*
 *****************/
switch slider {
	background-color: #363636;
}
switch {
	background-color: #686868;
}
switch:checked {
	background-color: @accent_bg_color;
}

checkbutton check:checked {
	color: #363636;
	background-color: @accent_bg_color;
}

scale highlight {
	background-color: #94ebeb;

}

scale slider {
	background-color: #94ebeb;
}

/*****************
 *CARDS/BOXEDLIST*
 *****************/

/*Borders to seperate foreground from background */
.card {
	border-radius: 5px;
	border-style: solid;
	border-width: 1px;
	border-color: @shade_color;
}

list.boxed-list  {
	border-radius: 5px;
	border-style: solid;
	border-width: 1px;
	border-color: @shade_color;
}

list.boxed-list row:not(:last-child):not(:first-child):only-child{
	border-radius: 0px;
}

/*nested rows are wierd and don't have a color*/
list.boxed-list row.expander row:last-child:not(:only-child) {
	background-color: #202020;
}

/*middle rows are straight*/
list.boxed-list row:not(:last-child):not(:first-child):hover{
	border-radius: 0px;
}

/*end rows are rounded at the bottom*/
list.boxed-list row:last-child, list.boxed-list row:last-child:hover {
	border-top-left-radius: 0px;
	border-top-right-radius: 0px;
	border-bottom-left-radius: 5px;
	border-bottom-right-radius: 5px;
}

/*begining rows are rounded at the top*/
list.boxed-list row:first-child,list.boxed-list row:first-child:hover {
	border-top-left-radius: 5px;
	border-top-right-radius: 5px;
	border-bottom-left-radius: 0px;
	border-bottom-right-radius: 0px;
}

list.boxed-list row.activatable:not(:last-child):not(:first-child):selected {
	color: @dark_5;
	background-color: #94ebeb;
	border-radius: 0px;
}

list.boxed-list row.activatable:last-child:selected{
	color: @dark_5;
	background-color: #94ebeb;
	border-top-left-radius: 0px;
	border-top-right-radius: 0px;
	border-bottom-left-radius: 5px;
	border-bottom-right-radius: 5px;
}

list.boxed-list row.activatable:first-child:selected {
	color: @dark_5;
	background-color: #94ebeb;
	border-top-left-radius: 5px;
	border-top-right-radius: 5px;
}

row.activatable:selected {
	color: @dark_5;
	background-color: #94ebeb;
}


list row.entry:only-child,list row.entry:only-child:hover {
	border-radius: 5px;
}
window {
	border-bottom-left-radius: 5px;
	border-bottom-right-radius: 5px;
	border-top-left-radius: 5px;
	border-top-right-radius: 5px;
}

/*Fixed Dialog Buttons */
window.background.csd.messagedialog .response-area button:first-child {
	border-bottom-left-radius: 5px;
}

window.background.csd.messagedialog .response-area button:last-child {
	border-bottom-right-radius: 5px;
}

scrollbar range trough slider:active {
	color: #94ebeb;
}


/***************
 *Viewswitcher *
 ***************/
viewswitcher button.flat.horizontal.toggle {
	margin-top: 0px;
	margin-bottom: 0px;
	border-radius: 0px;
}

viewswitcher button.flat.horizontal.toggle:hover {
	margin-top: 0px;
	margin-bottom: 0px;
	border-radius: 0px;
	box-shadow: inset 0px -4px darker(@headerbar_bg_color);
}

viewswitcher button.flat.horizontal.toggle:checked {
	margin-top: 0px;
	margin-bottom: 0px;
	border-radius: 0px;
	box-shadow: inset 0px -4px @accent_bg_color;
}

viewswitcher button.flat.horizontal.toggle box, viewswitcher button.flat.vertical.toggle box {
	margin-top: 2px;
}


revealer viewswitcher button.flat.vertical.toggle box {
	margin-top: 5px;
}

viewswitcher button.flat.vertical.toggle {
	margin-bottom: 0px;
	border-radius: 0px;
}

viewswitcher button.flat.vertical.toggle:hover {
	margin-bottom: 0px;
	border-radius: 0px;
	box-shadow: inset 0px -4px darker(@headerbar_bg_color);
}

viewswitcher button.flat.vertical.toggle:checked {
	margin-bottom: 0px;
	border-radius: 0px;
	box-shadow: inset 0px -4px @accent_bg_color;
}

/*When view switcher is at the bottom and narrow*/
revealer viewswitcher.narrow button.flat.vertical.toggle {
	margin-bottom: 0px;
	border-radius: 0px;
}

revealer viewswitcher.narrow button.flat.vertical.toggle:hover {
	margin-bottom: 0px;
	border-radius: 0px;
	box-shadow: inset 0px 4px darker(@headerbar_bg_color);
}

revealer viewswitcher.narrow button.flat.vertical.toggle:checked {
	margin-bottom: 0px;
	border-radius: 0px;
	box-shadow: inset 0px 4px @accent_bg_color;
}

/*******
 *TABS *
 *******/
tabboxchild {
	margin-top: 0px;
	margin-bottom: 0px;
	border-radius: 0px;
}

tabboxchild tab {
	border-radius: 0px;
}

tabboxchild tab:selected {
	border-radius: 0px;
	box-shadow: inset 0px -4px @accent_bg_color;
}

tabboxchild tab:hover:not(:selected) {
	border-radius: 0px;
	box-shadow: inset 0px -4px darker(@headerbar_bg_color);
}

tabthumbnail picture {
	border-radius: 5px;
}

popover contents {
	border-radius: 5px;
	border-style: solid;
	border-width: 1px;
	border-color: @shade_color;
}

/*******************
 *WINDOW DECORATION*
 *******************/

decoration {
	border-radius: 5px 5px 0 0;
}

window separator:first-child + headerbar:backdrop, window separator:first-child + headerbar, window headerbar:first-child:backdrop, window headerbar:first-child {
	border-top-left-radius: 5px;
}

window headerbar:last-child:backdrop, window headerbar:last-child {
	border-top-right-radius: 5px;
}

window stack headerbar:first-child:backdrop, window stack headerbar:first-child, window stack headerbar:last-child:backdrop, window stack headerbar:last-child {
	border-top-left-radius: 5px; border-top-right-radius: 5px;
}

.background .titlebar:backdrop, .background .titlebar {
	border-top-left-radius: 5px; border-top-right-radius: 5px; 
}

.csd menu, .csd .menu, .csd .context-menu {
	border-radius: 5px;
}
</code></pre>

</details>
</p>

Credits: halfmexican for the original GTK4 css

## To do

- Light theme
- More polish here and there
- Lock screen
- Fix bugs (you tell me)
