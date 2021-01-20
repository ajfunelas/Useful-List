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

[Public & Private Routes](https://medium.com/@thanhbinh.tran93/private-route-public-route-and-restricted-route-with-react-router-d50b27c15f5e)

[React State Management](https://medium.com/@thanhbinh.tran93/react-state-management-fb857a2432cf)

[Read later cuz you're too sleepy](https://medium.com/@gemisis/developing-for-vr-in-2020-a-beginners-guide-bde4bc2611fc)

[Breathing Animation](https://codepen.io/machi/pen/YymGzP?editors=1100)

[Main Menu Unity](https://www.youtube.com/watch?v=-GWjA6dixV4)

[Japan Train Chimes & Jingles](https://www.youtube.com/watch?v=UOJNh4_YSOw)

[React Hook Animations](https://www.youtube.com/watch?v=0q8htcovGUQ&ab_channel=LogRocket)

[Webpack-Bundle-Analyzer to check library file size](npmjs.com/package/webpack-bundle-analyzer)

[Proper Flutter Installation](https://www.youtube.com/watch?v=T9LdScRVhv8)

[Go env setup windows & mac](https://www.youtube.com/watch?v=dgIh-VYcWYw)

[Material UI loading examples](http://react-material.fusetheme.com/documentation/material-ui-components/progress)

[Firebase File Upload](https://dev.to/itnext/how-to-do-image-upload-with-firebase-in-react-cpj)

[Problem Solving](https://interestingengineering.com/how-to-think-like-a-programmer-when-problem-solving)

[SQL Game](https://mystery.knightlab.com/walkthrough.html)
