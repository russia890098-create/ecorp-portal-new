# 🚀 Deployment Checklist

## Pre-Deployment

- [ ] Copy `.env.example` to `.env`
- [ ] Set `SECRET_KEY`, `FLAG_KEY`, `ROOT_PASSWORD`, and `FLAG_1..FLAG_5`
- [ ] Test locally with `python app.py`
- [ ] Verify all vulnerabilities work
- [ ] Test guest login
- [ ] Confirm flag is encrypted properly
- [ ] Review code for unintended bugs

## GitHub Setup

- [ ] Create new repository
- [ ] Do not commit `.env`, `uploads/`, `ecorp.db`, `__pycache__/`, or `WALKTHROUGH.md`
- [ ] Commit: `git commit -m "Initial CTF challenge"`
- [ ] Push to GitHub

## Render Deployment

- [ ] Sign up/login to Render.com
- [ ] Create new Web Service
- [ ] Connect GitHub repository
- [ ] Set Build Command: `pip install -r requirements.txt && python init_db.py`
- [ ] Set Start Command: `gunicorn app:app`
- [ ] Add environment variables:
- `SECRET_KEY=<random session secret>`
- `FLAG_KEY=<random flag key>`
- `ROOT_PASSWORD=<random root password>`
- `FLAG_1=XPL8{group_1_flag}`
- `FLAG_2=XPL8{group_2_flag}`
- `FLAG_3=XPL8{group_3_flag}`
- `FLAG_4=XPL8{group_4_flag}`
- `FLAG_5=XPL8{group_5_flag}`
- `DECOY_FLAG=XPL8{fake_flag_i_require_something}` (optional)
- [ ] Confirm build logs show `python init_db.py` completed successfully
- [ ] Deploy and wait 3-5 minutes
- [ ] Test deployed URL

## Post-Deployment Testing

- [ ] Test guest login at deployed URL
- [ ] Verify SQL injection works
- [ ] Test 2FA bypass
- [ ] Confirm path traversal
- [ ] Test privilege escalation
- [ ] Verify flag decryption as root
- [ ] Check all UI elements render correctly

## CTF Platform Setup

- [ ] Add challenge to CTF platform
- [ ] Set difficulty: Medium
- [ ] Set points: 350
- [ ] Upload CHALLENGE_DESCRIPTION.md
- [ ] Configure hints (optional)
- [ ] Set flag: `XPL8{your_flag_here}`
- [ ] Test flag submission

## Documentation

- [ ] Keep WALKTHROUGH.md private (organizer only)
- [ ] Share README.md with participants
- [ ] Prepare hint release schedule if needed

## Monitoring

- [ ] Check deployment logs regularly
- [ ] Monitor for unintended exploits
- [ ] Be ready to trigger a redeploy if you need a full reset

---

## Quick Reset Command

If database gets corrupted:
```bash
python init_db.py
```

Or on Render, trigger manual redeploy.

---

## Emergency Contacts

- Render Support: support@render.com
- CTF Admin: [Your contact info]

---

**Status:** ⬜ Not Started | 🟡 In Progress | ✅ Complete
