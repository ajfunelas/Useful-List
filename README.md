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

```bash

cd .ssh
ssh-keygen -f github
cat github.pub
nano config
Host github.com
  IdentityFile ~/.ssh/github

```


```bash
docker exec -it foo-db psql -U foo
```

```sql
CREATE EXTENSION IF NOT EXISTS pg_trgm;
CREATE EXTENSION IF NOT EXISTS pgcrypto;
CREATE EXTENSION IF NOT EXISTS "uuid-ossp";
```

Keychron V2 fn keys fix for linux/ubuntu:
What I would try and do is change the fnmode variable on your system from the boolean 1 to 0. You should be able to do this by piping an echo 0 command to tee on the file itself:
```bash
echo 0 | sudo tee /sys/module/hid_apple/parameters/fnmode
```
If that doesn't work, remember to set it back to 1 for consistency's sake:
```bash
echo 1 | sudo tee /sys/module/hid_apple/parameters/fnmode
```

[Stripe Payment Integration](https://stripe.com/docs/checkout/integration-builder)

```go
type CheckoutSessionRequest struct {
	Params struct {
		SuccessURL string `json:"successURL"`
		CancelURL  string `json:"cancelURL"`
	} `json:"params"`
	Payload struct {
	} `json:"payload"`
}

// CheckoutSession generates a checkout session and return its ID
func (c *StripeController) CheckoutSession(w http.ResponseWriter, r *http.Request, u *db.User) (int, error) {
	req := &CheckoutSessionRequest{}
	err := json.NewDecoder(r.Body).Decode(req)
	if err != nil {
		return http.StatusBadRequest, terror.New(err, "invalid input")
	}
	defer r.Body.Close()

	_, err = c.CreateStripeCustomer(w, r, u)
	if err != nil {
		return http.StatusInternalServerError, terror.New(err, "failed to create new stripe customer")
	}

	// productID := "insert productID"
	priceID := "insert priceID"

	// Get Checkout Session
	params := &stripe.CheckoutSessionParams{
		Customer: &u.StripeCustomerID.String,
		// SuccessURL: stripe.String("https://example.com/success"),
		// CancelURL:  stripe.String("https://example.com/cancel"),
		CancelURL:  &req.Params.CancelURL,
		SuccessURL: &req.Params.SuccessURL,
		PaymentMethodTypes: stripe.StringSlice([]string{
			"card",
		}),
		LineItems: []*stripe.CheckoutSessionLineItemParams{
			{
				Price:    stripe.String(priceID),
				Quantity: stripe.Int64(1),
			},
		},
		Mode: stripe.String(string(stripe.CheckoutSessionModeSubscription)),
	}

	fmt.Println(params)

	session, err := c.stripeClient.CheckoutSessions.New(params)
	if err != nil {
		return http.StatusInternalServerError, terror.New(err, "failed to get billing portal")
	}

	return helpers.EncodeJSON(w, session.ID)
}
```

[Favicon generator for react projects](https://favicomatic.com/)


```go
func (c *OpportunityController) SendEmailNotification(w http.ResponseWriter, r *http.Request, u *db.User) (int, error) {
	id := chi.URLParam(r, "id")
	_, err := uuid.FromString(id)
	if err != nil {
		return http.StatusInternalServerError, terror.New(err, "")
	}

	selectedProposals, err := db.Proposals(
		db.ProposalWhere.OpportunityID.EQ(id),
		db.ProposalWhere.IsSelected.EQ(true),
		qm.Load(
			db.ProposalRels.Poster,
		),
		qm.Load(
			qm.Rels(
				db.ProposalRels.Opportunity,
				db.OpportunityRels.Business,
				db.BusinessRels.Owner,
			),
		),
	).All(c.Conn)
	if err != nil {
		return http.StatusInternalServerError, terror.New(err, "")
	}
	fmt.Println("hit hello")

	for _, sp := range selectedProposals {

		businessName := sp.R.Opportunity.R.Business.Name

		fmt.Println(businessName)

		// Create email
		subject := "Congratulations, " + businessName + " business want to chat"

		name := "UserDetail"
		if u.FirstName != "" {
			name = u.FirstName
		}
		if u.LastName != "" {
			name += " " + u.LastName
		}

		message := c.mailer.NewMessage(c.mailHost.Sender, subject, "", sp.R.Poster.Email)
		message.SetTemplate("experlio_notification")

		fmt.Println("hit hello")

		message.AddVariable("name", sp.R.Poster.FirstName)

		message.AddVariable("business", sp.R.Opportunity.R.Business.Name)
		message.AddVariable("owner_name", sp.R.Opportunity.R.Business.R.Owner.FirstName)
		message.AddVariable("owner_email", sp.R.Opportunity.R.Business.R.Owner.Email)

		// Send Email
		emailCtx, cancel := context.WithTimeout(context.Background(), time.Second*10)
		defer cancel()

		_, _, err = c.mailer.Send(emailCtx, message)

		if err != nil {
			return http.StatusInternalServerError, terror.New(err, "fail to send email")
		}

	}

	return helpers.EncodeJSON(w, true)
}
```

