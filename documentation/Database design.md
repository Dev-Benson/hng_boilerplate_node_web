Table User {
  user_id Integer [pk, increment]
  name Varchar
  email Varchar [unique]
  password Varchar
  role Varchar
  profile_picture Varchar
  auth_type Varchar
  auth_provider Varchar
  auth_token Varchar
  gdpr_consent Boolean
  status Varchar
  last_login Timestamp
  created_at Timestamp
  updated_at Timestamp
}

Table UserSettings {
  setting_id Integer [pk, increment]
  user_id Integer [ref: > User.user_id]
  key Varchar
  value JsonB
  created_at Timestamp
  updated_at Timestamp
}

Table Organisation {
  org_id Integer [pk, increment]
  name Varchar
  description Text
  created_by Integer [ref: > User.user_id]
  status Varchar
  created_at Timestamp
  updated_at Timestamp
}

Table UserOrganisation {
  user_id Integer [ref: > User.user_id]
  org_id Integer [ref: > Organisation.org_id]
  role Varchar
  joined_at Timestamp
}

Table Content {
  content_id Integer [pk, increment]
  title Varchar
  slug Varchar
  content Text
  author_id Integer [ref: > User.user_id]
  type Varchar
  status Varchar
  published_at Timestamp
  created_at Timestamp
  updated_at Timestamp
}

Table Notification {
  notification_id Integer [pk, increment]
  user_id Integer [ref: > User.user_id]
  type Varchar
  message Text
  read_status Boolean
  created_at Timestamp
}

Table Email {
  email_id Integer [pk, increment]
  user_id Integer [ref: > User.user_id]
  subject Varchar
  body Text
  status Varchar
  sent_at Timestamp
}

Table Payment {
  payment_id Integer [pk, increment]
  user_id Integer [ref: > User.user_id]
  org_id Integer [ref: > Organisation.org_id]
  amount Decimal(10, 2)
  currency Varchar
  payment_provider Varchar
  status Varchar
  transaction_id Varchar
  created_at Timestamp
}

Table ActivityLog {
  log_id Integer [pk, increment]
  user_id Integer [ref: > User.user_id]
  org_id Integer [ref: > Organisation.org_id]
  activity_type Varchar
  description Text
  ip_address Varchar
  user_agent Varchar
  created_at Timestamp
}

Table Invite {
  invite_id Integer [pk, increment]
  inviter_id Integer [ref: > User.user_id]
  invitee_email Varchar
  org_id Integer [ref: > Organisation.org_id]
  status Varchar
  invite_token Varchar
  created_at Timestamp
  expires_at Timestamp
}

Table AIInteraction {
  interaction_id Integer [pk, increment]
  user_id Integer [ref: > User.user_id]
  type Varchar
  input Text
  output Text
  model_used Varchar
  created_at Timestamp
}

Table ExportJob {
  job_id Integer [pk, increment]
  user_id Integer [ref: > User.user_id]
  type Varchar
  status Varchar
  file_url Varchar
  created_at Timestamp
  completed_at Timestamp
}

Table PasswordReset {
  reset_id Integer [pk, increment]
  user_id Integer [ref: > User.user_id]
  token Varchar
  expires_at Timestamp
  created_at Timestamp
}

Table EmailTemplate {
  template_id Integer [pk, increment]
  name Varchar
  subject Varchar
  body Text
  variables JsonB
  created_at Timestamp
  updated_at Timestamp
}

Table Waitlist {
  id Integer [pk, increment]
  email Varchar
  name Varchar
  status Varchar
  signed_up_at Timestamp
}

ADDITIONS WITH CONSIDERATIONS FOR SCALE --------------

Table AIInteractionMeta {
  meta_id Integer [pk, increment]
  interaction_id Integer [ref: > AIInteraction.interaction_id]
  key Varchar
  value Text
}

Table PaymentMeta {
  meta_id Integer [pk, increment]
  payment_id Integer [ref: > Payment.payment_id]
  key Varchar
  value Text
}

Table ContentMeta {
  meta_id Integer [pk, increment]
  content_id Integer [ref: > Content.content_id]
  key Varchar
  value Text
}

Table Tag {
  tag_id Integer [pk, increment]
  name Varchar
  created_at Timestamp
}

Table ContentTag {
  content_id Integer [ref: > Content.content_id]
  tag_id Integer [ref: > Tag.tag_id]
}


Example Usage for (the some-what vague named) key-value fields
UserSettings & Meta tables (UserSettings, ContentMeta, PaymentMeta, AIInteractionMeta) can use the key-value field to store
additional/variable, information related to their parent table.
makes adding new attributes possible without having to alter the main table structure.

UserSettings:
Key: "language", Value: "en-US"
Key: "theme", Value: "dark"
Key: "notification_preferences", Value: {"email": true, "push": false} - this will be in json format so it'll be text like and can be stored in relational db

ContentMeta:
Key: "seo_description", Value: "A comprehensive guide to database design"
Key: "featured_image", Value: "https://example.com/images/featured.jpg"
Key: "read_time", Value: "5 minutes"

PaymentMeta:
Key: "customer_ip", Value: "192.168.1.1"
Key: "billing_address", Value: {"street": "123 Main St", "city": "Anytown", "zip": "12345"}
Key: "promo_code", Value: "SUMMER2023"

AIInteractionMeta:
Key: "confidence_score", Value: "0.95"
Key: "processing_time", Value: "1.23 seconds"
Key: "source_data", Value: "user_input_7382"
