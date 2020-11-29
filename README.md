# Useful-List
A list of useful links

[Setting up git credentials](https://www.shellhacks.com/git-config-username-password-store-credentials/)

[Copy Text with Pure JS](https://stackoverflow.com/questions/33855641/copy-output-of-a-javascript-variable-to-the-clipboard)

```javascript
function textToClipboard (text) {
    var dummy = document.createElement("textarea");
    document.body.appendChild(dummy);
    dummy.value = text;
    dummy.select();
    document.execCommand("copy");
    document.body.removeChild(dummy);
}
```
[Timelapse Render Lumix](https://www.fourthirds-user.com/forum/forum/equipment/panasonic-lumix-cameras/15003-lumix-g7-time-lapse-after-the-fact?14542-Lumix-G7-Time-Lapse-after-the-fact=)

[PostgreSQL audit logging using triggers](https://vladmihalcea.com/postgresql-audit-logging-triggers/)

For Users: >

```go
		for i := 0; i < 5; i++ {
			u := store.UserFactory()
			u.RoleID = member.ID
			err := u.Insert(conn, boil.Infer())
			if err != nil {
				return fmt.Errorf("%w", err)
			}
		}

```


[json to interface](http://json2ts.com/)

[Simple Box Shadows](https://codepen.io/sdthornton/pen/wBZdXq)

[Jamie's Shadow Realm](https://xd.adobe.com/view/6e25d7ab-d974-4387-980f-360f3962759c-3b76/specs/)

[How to get changes from another branch](https://stackoverflow.com/questions/37709298/how-to-get-changes-from-another-branch)

[CLI Migration](https://github.com/golang-migrate/migrate/blob/master/GETTING_STARTED.md)

[RPG Like Map](https://www.youtube.com/watch?v=T1masuI3g8Q)

[Agawan base mechanics](https://askinglot.com/what-is-the-mechanics-of-agawan-base)

[Tilemapping in Unity](https://www.youtube.com/watch?v=ryISV_nH8qw)
